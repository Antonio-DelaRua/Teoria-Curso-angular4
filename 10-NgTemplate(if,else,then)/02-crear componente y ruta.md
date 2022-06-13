para hacer este ejemplo que vamos a hacer nos vamos a hacer un nuevo componente y una nueva ruta para probar todos los ngtemplate :

vamos a nuestro app y creamos :

plantillas 

creamos un nuevo fichero q se va a llamar : 

plantillas.component.html y plantillas.component.ts


en el fichero de plantillas.component.ts quedaria asi : 

import { Component } from "@angular/core";


@Component({
    selector: 'plantillas',
    templateUrl: './plantillas.component.html'
})

export class plantillasComponent{

    public titulo;
    public administrador;

    constructor(){

        this.titulo = "Plantillas ngTemplate en Angular";
        this.administrador = true;
    }

    cambiar(value:boolean){

        this.administrador = value;
    }
}

y el fichero de plantillas.component.html quedaria asi :

<h4>{{titulo}}</h4>
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
es otra forma de hacerlo 
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

<!-- <div *ngIf="administrador; Else noAdmin">
 <button (click)="cambiar(false)">cambiar</button>

  <strong style="background:yellow;">Eres el administrador de la webapp</strong>

</div>

<div *ngIf="!administrador">

    <strong style="background:red;color:white">NO eres el administrador de la webapp</strong>
  
</div> -->

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
<div *ngIf="administrador; then admin else noAdmin"></div>
<ng-template #admin>
    <button (click)="cambiar(false)">cambiar</button>

  <strong style="background:yellow;">Eres el administrador de la webapp</strong>



</ng-template>

<ng-template #noAdmin>
    <button (click)="cambiar(true)">cambiar</button>

    <strong style="background:red;color:white">NO eres el administrador de la webapp</strong>

</ng-template>

para crear la ruta vamos al app.routing.ts y vamos a importar nuestro componente

import { plantillasComponent } from "./plantillas/plantillas.component";

dentro de este fichero le creamos una ruta :

{path: 'plantillas', component: plantillasComponent},

tambien tenemos que ir al app.module.ts para importarlo :

import { plantillasComponent } from './plantillas/plantillas.component';

y lo declaramos :

plantillasComponent



ahora le añadimos un nuevo complemento al menu que eso lo tenemos en el app.component.html:

 <a [routerLink]="['/plantillas']" [routerLinkActive]="['activado']">
        Plantillas
     
     </a>


