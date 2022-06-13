definicion:
son clases con un objetivo claro que nos facilita la reutalizacion de codigo, son un tipo de componente o una parte de arquitectura de la aplicacion que nos va a permitir separar un poco de logica del componente y llevarnosla al servicio.

vamos a utilizar el componente home porque es un componente que tenemos vacio

creamos una carpeta dentro de app q se llame 
services
dentro creamos un fixero que se llame ropa.service.ts

import { Injectable } from "@angular/core";



@Injectable()
export class RopaService{
    public nombre_prenda = 'Pantalones vaqueros';

    prueba(nombre_prenda:string){
        return nombre_prenda;
    }


la vamos a utilizar con el componente home

vamos a home.component.ts
lo primero que tenemos que hacer es importar el servicio:

import { RopaService } from "../services/ropa.service";

ahora como cargamos este servicio dentro de nuestro componente :

con el providers:

 providers: [RopaService]

 ahora tenemos que crear una propiedad en la cual se instancie este objeto para poder utilizarlo:

 export class HomeComponent{

    constructor(
        private _ropaService: RopaService
    ){ }

    de esta forma ya tengo una instancia de ropa service inyectada en la clase

    ahora con el metodo ngOnInit:

     ngOnInit(){

        console.log(this._ropaService.prueba('camiseta nike'));
    }

nos devolvera el contenido correctamente en la consola.

normalmente lo utilizaremos para hacer algun metodo que nos procese algun dato ...





