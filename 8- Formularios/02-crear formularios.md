lo primero que vamos a hacer es crear un componente o utilizar uno que ya exista .

vamos a app y creamos un nuevo folder que se va a llamar coches.

dentro de esa carpeta creamos un fixero que se va a llamar coche.component.ts

ahora nos metemos dentro y importamos lo necesario :

import { Component } from '@angular/core';


@Component({

    selector: 'coches',
    templateUrl: './coches.component.html'

})

export class CochesComponent{


}

lo siguiente seria crear nuestra plantilla html : coches.component.html

<h1>Componente de coche</h1>

lo siguiente seria crear una nueva ruta para este componente (path): vamos a app.routing.ts:

{path: 'coches', component: CochesComponent},

tb tenemos que importar el componente coches:

import { CochesComponent} from './coches/coches.component';

ahora lo importamos tambien en el app.module.ts:

import { CochesComponent} from './coches/coches.component';

lo cargamos tambien dentro de declarations: 

CochesComponent

y ahora ya podremos utilizar la ruta.

nos vamos a app.component.html:

y vamos a crear un link a coches :

<a [routerLink]="['/coches']" [routerLinkActive]="['activado']>
   Coches

</a>

ahora vamos a crear un formulario :

creamos una carpeta que sea coche.ts y aqui vamos a crear un objeto al igual que hemos creado el de empleado:

export class Coche{
    constructor(
        public nombre:string,
        public caballaje:string,
        public color:string,
    ){}
}

asi ya tendriamos nuestra clase de coche creada tendriamos que importarlo en nuestro componente, coches.component.ts:

import { Component } from '@angular/core';
import { Coche} from './coche';

ahora vamos a crearnos una propiedad publica que se va a llamar coche y va a ser un objeto de tipo coche:

export class Coches component {
    public coche: Coche;
}


ahora en el constructor vamos a asignarle un valor a esa propiedad :

export class Coches component {
    public coche: Coche;
}

constructor(){
    this.coche = new Coche("","","");
}

ahora vamos a crear el formulario nos vamos a coches.component.html:

<h1>Componente de coche</h1>

<form #formCoche="ngForm">
   <label>Nombre:</label>
   <input type="text">

   <label>Nombre:</label>
   <input type="text">

   <label>Nombre:</label>
   <input type="text">

   <imput type="submit" value="Guardar">
</form>

ahora lo metemos en la etiqueta <p> para que salte de linea:

<form #formCoche="ngForm">
<p>
   <label>Nombre:</label>
   <input type="text">

</p>

<p>
   <label>Nombre:</label>
   <input type="text">
</p>   

 <p>  

   <label>Nombre:</label>
   <input type="text">

</p>   

   <imput type="submit" value="Guardar">
</form>


ahora lo que vamos a hacer es vincular este objeto que tenemos en el componente lo vamos a vincular con el formulario:

<form #formCoche="ngForm">
<p>
   <label>Nombre:</label>
   <input type="text" name="nombre" #nombre="ngModel" [(ngModel)]="coche.nombre" required>

</p>

<p>
   <label>Nombre:</label>
   <input type="text"name="caballaje" #caballaje="ngModel" [(ngModel)]="coche.caballaje" required>
</p>   

 <p>  

   <label>Nombre:</label>
   <input type="text"name="color" #color="ngModel" [(ngModel)]="coche.color" required>

</p>   

   <imput type="submit" value="Guardar">
</form>


ahora para que todo esto funcione lo que vamos a hacer es utilizar el evento summit:

<form #formCoche="ngForm" (ngSubmit)="onSubmit()">
<p>
   <label>Nombre:</label>
   <input type="text" name="nombre" #nombre="ngModel" [(ngModel)]="coche.nombre" required>

</p>

<p>
   <label>Nombre:</label>
   <input type="text"name="caballaje" #caballaje="ngModel" [(ngModel)]="coche.caballaje" required>
</p>   

 <p>  

   <label>Nombre:</label>
   <input type="text"name="color" #color="ngModel" [(ngModel)]="coche.color" required>

</p>   

   <imput type="submit" value="Guardar">
</form>

lo siguiente sera crear nuestro metodo en nuestro componente (coches.component.ts):

export class Coches component {
    public coche: Coche;
}

constructor(){
    this.coche = new Coche("","","");
}

onSubmit(){}

para ver que los datos funcionan correctamente podemos poner :

export class Coches component {
    public coche: Coche;
}

constructor(){
    this.coche = new Coche("","","");
}

onSubmit(){
    console.log(this.coche);
}

