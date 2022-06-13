vamos a approuting.ts 

{path: 'contacto/:page', component: contactoComponent},

ahora para recoger el parametro de nuestro componente y poder utilizarlo.

vamos a contacto.component.ts

voy a importar los modules necesarios para trabajar

import { Router, ActivatedRoute, Params } from "@angular/router";

exportamos la clase

public parametro:any;
 
activamos los modulos :

constructor(
      private _route: ActivatedRoute, 
      private _router: Router
      ){}

como recogemos ese parametro de la url :
ngOnInit() {
    this._route.params.forEach((params: Params) => {
      this.parametro = params['page'];
    });
  }
}

funcion de calva (fuction)**
funcion de flecha =>**


vamos a  contacto.component.html

Parametro de la Url:{{parametro}}

si queremos que nos muestre el texto de parametro de la url solo cuando haya un parametro vamos a la carpeta contacto.component.html y dentro de un div ponemos el comando if

<div *ngIf="parametro">
Parametro de la Url:{{parametro}}
</div>


