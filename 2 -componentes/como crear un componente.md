


-creamos una carpeta “name” detro de la app. http://localhost:4200/
-creamos un fichero dentro de la carpeta que hemos creado …..component.ts
-dentro de name.component.ts escribimos 
import {component} from ‘@angular/core’;

@component ({
  selector: ‘empleado-tag’;        ponemos el selector para indicar la etiqueta componente 
   templateUrl: ‘./empleado.component.html  dirigimos la carpeta del contenido

}]

-export class EmpleadoComponent {

public titulo = ‘titulo del componente empleado’;

}

-lo siguiente creamos la carpeta html dentro de la carpeta del componente que hemos creado ( empleado.component.html)

ponemos dentro de la carpeta empleado.component.html:

<h1 style="blue;">{{titulo}}</h1>

el estilo solo es para reconocerlo.

-lo siguiente sera ir a app.module.ts a importar el componente :

import { EmpleadoComponent } from './empleado/empleado.component';

y lo declaramos : 

declarations: 
EmpleadoComponent




-entramos a app.component.html :

y copiamos el selector en el html de la app principal : 

<empleado-tag></empleado-tag>

 
ya tenemos la etiqueta creada. La podriamos utilizar dentro de cualquier otro componente

ej: pueo poner la etiqueta dentro de fruta.component.html:

EMPLEADO:<empleado-tag></empleado-tag>
