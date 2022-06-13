ahora vamos a crear nuestros propios pipes :

lo primero creamos una nueva carpeta dentro de app que se llame pipes.

despues creamos nuestro fixero: conversor.pipe.ts

lo primero que tenemos que hacer es importar los paquetes de pipe que nos va a permitir trabajar con ellos :

import {Pipe, PipeTransform} from "@angular/core";

creamos nuestro decorador:que nos va a permitir ponerle el nombre a nuestro pipe

@pipe({ name: 'conversor'})

despues exportamos la clase :
 
export class ConversorPipe 

tambien tenemos que implementar la interfaz PipeTransform

export class ConversorPipe implements PipeTransform{
    transform(){

    }
}

en este metodo nosotros lo que vamos hacer va a ser pasarle una serie de parametros que va a ser lo que la pipe va a estar procesando y aqui es donde se va ejecutar toda la logica de la pipe:

export class ConversorPipe implements PipeTransform{
    transform(value, por){
          let value_one = parseInt(value);
          let value_two = parseInt(por);

          let result = "La multiplicacion: "+value_one+"x"+valuetwo+" = "+(value_one * value_two);

          return result;
    }
}


de momento esta pipe no la estamos implementando en ningun sitio por lo cual ahora vamos a introducirla de manera global en nuestra aplicacion :

nos vamos a app.module.ts y aqui importamos mi pipe:

import { ConversorPipe } from './pipes/conversor.pipe';

y ahora lo que tengo que hacer es meter este conversor de declaration :

@NgModule({
    ConversorPipe
})


ahora si vamos a home.component.html y tratamos de imprimir:

{{5 | conversor: 7}}

5 seria = a nuestro value y 7 al por



