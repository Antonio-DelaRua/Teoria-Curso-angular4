
vamos a la carpeta de services:


dentro de services creamos peticiones.services.ts:


lo primero es importar el modulo injectable que nos va a permitir la injeccion de dependencia y el decorador injectable:

import { Injectable} from '@angular/core';

ahora vamos a importar los modulos HTTP:

import { Http, Response, Headers } from '@angular/http';

ahora importamos una libreria para mapear esa respuesta http que se llama RX JS:

import 'rxjs/add/operator/map';

y por ultimo importamos el observable:

import { Observable } from 'rxjs/observable';


ahora utilizamos el decorador injectable  y definimos nuestra clase export:

@Injectable()
export class PeticionesService{
    getPrueba(){
        return'hola que ase';
    }
}

ahora nos vamos a cualquier componente nos vamos al de coches ya que es el ultimo en utilizarlo coches.component.ts:

import { PeticionesService } from '../services/peticiones.service';

y ahora cargamos los servicios con los providers:

@component(){
    providers: [PeticionesService]
}

lo siguiente ser irse al constructor : 
(
private _peticionesService: PeticionesService
)

