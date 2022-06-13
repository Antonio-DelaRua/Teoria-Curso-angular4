ahora vamos a hacer un evento parecido al que tenemos en la home con objetos que nos va generando pero esta vez lo vamos a hacer con nuestro formulario de coches:


vamos a coches.component.ts y vamos a crear una array:

public coches:Array<coche>;

constructor(){
    this.coches = [
        new Coche("Seat Panda","120","Blanco")
        new Coche("Renault Clio","200","azul")
    ];
}

lo siguiente serie ir a coches.component.html:

<div style="">
   <h4>Listado de coches</h4>
   <ul>
   <li *ngFor='let coche of coches'>
        {{coche.nombre}}--{{coche.caballaje}}--{{coche.color}}
   </li>
   </ul>     

</div>

ahora vamos a mover visualmente nuestra lista:

<h1>Componente de coche</h1>

<style>
div{
    float:left;
}  

.listado{
    margin-left: 30px;
}

form{
    width: 200px;
      
}

input[type="text"], span{
    display:block;
    width: 100%;
}
</style>    

<div>



<form #formCoche="ngForm" (ngSubmit)="onSubmit()">
   <p>
      <label>Nombre:</label>
      <input type="text" name="nombre" #nombre="ngModel" [(ngModel)]="coche.nombre" required>
      <span *ngIf="nombre.touched && !nombre.valid">
         El nombre del coche es incorrecto!!

      </span>


   </p>

   <p>
      <label>caballaje:</label>
      <input type="text" name="caballaje" #caballaje="ngModel" [(ngModel)]="coche.caballaje" required pattern="[0-9]+">
      <span *ngIf="caballaje.touched && !caballaje.valid">
         El caballaje del coche es incorrecto!!

      </span>
   </p>

   <p>

      <label>color:</label>
      <input type="text" name="color" #color="ngModel" [(ngModel)]="coche.color" required pattern="[a-zA-Z#]+">
      <span *ngIf="color.touched && !color.valid">
         el color del coche es incorrecto!!
      </span>


   </p>

   <input type="Submit" value="Guardar">

</form>


<div class="listado">
<h4>Listado de coches</h4>
   <ul>
   <li *ngFor='let coche of coches'>
        {{coche.nombre}}-{{coche.caballaje}}-{{coche.color}}
   </li>
   </ul>     

   </div>

ahora lo que vamos a hacer es al enviar el formulario que tiene datos dentro y guardarlo en el listado. como comprobamos que todo es valido y que esta todo relleno , podemos ponerle un atributo que ponga disable cuando los parametros no sean correctos. podemos ponerle el atributo disable en el boton de guardar:


<input type="Submit" value="Guardar"[disabled]=>"!formCoche.form.valid">

ahora para en vez de q no los saque a la consola y lo ponga en la pag vamos a coches.component.ts :

onSubmit(){
    this.Coches.push(this.coche);
  
}

para que cuando nosotros guardemos nuestros datos se queden otra vez vacio :


onSubmit(){
    this.Coches.push(this.coche);
    this.Coche = new coche("","","");
  
}


como podemos mejorar la manera una vez que vaciamos el formulario para que no nos salte el error :

en la carpeta coches.component.html :tenemos que poner un evento click en el submit:

<form #formCoche="ngForm" (ngSubmit)="onSubmit(); formCoche.reset();">

