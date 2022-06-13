 vamos a mostrar un listado de prendas y que podamos añadir y eleminar elementos utilizando el two way data binding :

 primero nos vamos a ropa.service.ts

añadimos la array

public coleccion_ropa = ['Pantalones Blancos', 'Camiseta roja'];

despues definimos un metodo que añada al elemento de la array:

addRopa(nombre_prenda:string):Array<string>{
        this.coleccion_ropa.push(nombre_prenda);

despues nos hacemos otro metodo :
getRopa(){
        return this.coleccion_ropa;
    }

tambien podemos ponerle el return a addropa y asi nos devolvera algo en caso de que no haya nada

return this.coleccion_ropa;

lo siguiente seria ir a la carpeta home y home.component.ts:

lo primero que vamos a hacer es llamar al servicio para sacar el listado de ropa :

public listado_ropa:Array<string> 
lo siguiente :

ngOnInit(){
        
        this.listado_ropa = this._ropaservice.getRopa();console.log(this._ropaservice.prueba('camiseta nike'));

despues nos vamos a home.component.html y creamos el listado:

<br/>
 <input type="text" [(ngModel)]="prenda_a_guardar">
 
 <button (click)="guardarPrenda()">añadir prenda</button>

 <p *ngIf="prenda_a_guardar">La prendra a guardar es: <strong>{{prenda_a_guardar}}</strong></p>





<h3>Listado de prendas</h3>

<ul>

    <li *ngFor="let prenda of listado_ropa; let i = index">
       {{prenda}}
       <button (click)="eliminarPrenda(i)">eliminar</button>

    </li>

</ul>

que no se nos olvide crear en home.component.ts:


public prenda_a_guardar:any; le pongo any porque me da conflicto si le pongo string y con any cubrimos todas las posibilidades despues la iniciamos en el constructor:

  this.prenda_a_guardar ="";

asi quedarian las 3 archivos que hemos utilizado : 

ropa.service.ts:

import { Injectable } from "@angular/core";




@Injectable()
export class RopaService{
    public nombre_prenda = 'Pantalones vaqueros';
    public coleccion_ropa = ['Pantalones Blancos', 'Camiseta roja'];

    prueba(nombre_prenda:string){
        return nombre_prenda;
    }

    addRopa(nombre_prenda:string):Array<string>{
        this.coleccion_ropa.push(nombre_prenda);
        return this.getRopa();
    }

    deleteRopa(index:number){

        this.coleccion_ropa.splice(index, 1);
        return this.getRopa();
    }

    getRopa(){
        return this.coleccion_ropa;
    }
    
}

home.component.html:

<h2>{{titulo}}</h2>

<br/>
 <input type="text" [(ngModel)]="prenda_a_guardar">
 
 <button (click)="guardarPrenda()">añadir prenda</button>

 <p *ngIf="prenda_a_guardar">La prendra a guardar es: <strong>{{prenda_a_guardar}}</strong></p>



<h3>Listado de prendas</h3>

<ul>

    <li *ngFor="let prenda of listado_ropa; let i = index">
       {{prenda}}
       <button (click)="eliminarPrenda(i)">eliminar</button>

    </li>

</ul>


home.component.ts:

import { Component } from "@angular/core";
import { RopaService } from "../services/ropa.service";



@Component ({
         selector: 'home',
         templateUrl: './home.component.html',
         providers: [RopaService]
})

export class HomeComponent{
    public titulo = "Pagina principal";


    public listado_ropa:Array<string> 
    public prenda_a_guardar:any;

    tambien lo podemos hacer de este modo :lo que esta entre barras :
    ///////////////////////////////////////////////
    // public listado_ropa:Array<string>;
    // public prenda_a_guardar:string;
    // private _ropaservice: RopaService;

    // constructor(){ 
    //     this._ropaservice = new RopaService();
    //     this.prenda_a_guardar = "";
    //     this.listado_ropa = [];
    // }
    //////////////////////////////////////////////////

    constructor(
       
      
        private _ropaservice: RopaService
    ){
        this.listado_ropa =[];
        this.prenda_a_guardar ="";

    }

    ngOnInit(){
        
        this.listado_ropa = this._ropaservice.getRopa();

        console.log(this._ropaservice.prueba('camiseta nike'));
    }
    guardarPrenda(){
        this._ropaservice.addRopa(this.prenda_a_guardar);
        this.prenda_a_guardar = null;
    }

    eliminarPrenda(index:number){
        this._ropaservice.deleteRopa(index);
      alert(index);

    }

}
 