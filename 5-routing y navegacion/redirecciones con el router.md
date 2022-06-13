para q el parametro de la url no exista aparezca un boton q si tiene un parametro

vamos a la carpeta contacto.component.ts 

<div *ngIf="!parametro">
    
    <button (click)="redirigir()">Ir a la pagina con parametro</button>
    <button (click)="redirigirDos()">Ir a home</button>

</div>

creamos el metodo redirigir y redirigir2 en contacto.components.ts

redirigir(){
    this._router.navigate(['/contacto', 'ruxxdesing.site']);
  }
  redirigirDos(){
    this._router.navigate(['/home']);
  }