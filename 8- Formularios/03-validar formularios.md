como podemos poner el mensaje de error cuando se produzca :

vamos a coches.component.html:

<span *ngIf="nombre.touched && !nombre.valid">
       El nombre del coche es incorrecto!!

</span>       

quedaria asi : 

<form #formCoche="ngForm" (ngSubmit)="onSubmit()">
<p>
   <label>Nombre:</label>
   <input type="text" name="nombre" #nombre="ngModel" [(ngModel)]="coche.nombre" required>
   <span *ngIf="nombre.touched && !nombre.valid">
       El nombre del coche es incorrecto!!

</span>       

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


vamos a validar el siguiente campo que le podemos poner un patern que es una expresion regular y podemos decirle que solamente acepte carcteres del 0 al 9 y que ademas se repita mas de una vez:

required pattern="[0-9]+">
<span *ngIf="caballaje.touched && !caballaje.valid">
       El caballaje del coche es incorrecto!!

       quedaria asi : //////////////////////////////////////////////////////////////////////////////////////

<form #formCoche="ngForm" (ngSubmit)="onSubmit()">
<p>
   <label>Nombre:</label>
   <input type="text" name="nombre" #nombre="ngModel" [(ngModel)]="coche.nombre" required>
   <span *ngIf="nombre.touched && !nombre.valid">
       El nombre del coche es incorrecto!!

</span>       

</p>

<p>
   <label>Nombre:</label>
   <input type="text"name="caballaje" #caballaje="ngModel" [(ngModel)]="coche.caballaje" 
    required pattern="[0-9]+">
   <span *ngIf="caballaje.touched && !caballaje.valid">
       El nombre del coche es incorrecto!!

</p>   

 <p>  

   <label>Nombre:</label>
   <input type="text"name="color" #color="ngModel" [(ngModel)]="coche.color" required>

</p>   

   <imput type="submit" value="Guardar">
</form>



ahora vamos a hacer lo mismo pero con el color:
required pattern="[a-zA-Z#]+">
<span *ngIf="color.touched && !color.valid">
el color del coche es incorrecto!!
</span>
