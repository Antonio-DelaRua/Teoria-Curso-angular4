vamos a crear unos botones donde podamos ir a nuestros componentes

creamos 2 carpetas dentro de app

home 

contacto

dentro de home creamos 
 
home.component.ts

import { Component } from "@angular/core";


@Component ({
         selector: 'home',
         templateUrl: './home.component.html'
})

export class HomeComponent{
    public titulo = 'Pagina principal'

}
creamos el fixero Home.component.html

ponemos la clase dentro del fixero

<h2>{{titulo}}</h2>

ahora vamos a hacer lo mismo con la carpeta contacto 

creamos home.component.ts

import { Component } from "@angular/core";


@Component ({
         selector: 'contacto',
         templateUrl: './contacto.component.html'
})

export class contactoComponent{
    public titulo = 'Pagina principal'

}

despues creamos 

contacto.component.html
<h2>{{titulo}}</h2>