




para crear un boton con reaccion :


<div *ngIf="trabajador_externo == true">
<ul>
<button (click)="CambiarExterno(false)">Mostrar empleado</button>
<li>{{trabajadores[0].nombre}}</li>
<li>{{trabajadores[0].edad}}</li>
<li>{{trabajadores[0].cargo}}</li>
<li *ngIf="trabajadores[0].contratado == true">Esta contratado</li> 
<li *ngIf="trabajadores[0].contratado == false">No Esta contratado</li>
</ul>
</div>
<div *ngIf="trabajador_externo == false">
<ul>
<button (click)="CambiarExterno(true)">Mostrar trabajador</button>
<li>{{empleado.nombre}}</li>
<li>{{empleado.edad}}</li>
<li>{{empleado.cargo}}</li>
<li *ngIf="empleado.contratado == true">Esta contratado</li>
<li *ngIf="empleado.contratado == false">No esta contratado</li>
</ul>
</div>


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


export class Empleadocomponent {
public titulo = 'componente empleados:';
public empleado: Empleado;
public trabajadores: Array<Empleado>;
public trabajador_externo: boolean;

constructor() {
this.empleado = new Empleado('david', 45, 'cocinero', true);
this.trabajadores = [
new Empleado('manolo', 35, 'administrativo', false),
new Empleado('david', 45, 'cocinera', true),
];
this.trabajador_externo = true;
}

NgOninit() {
console.log(this.empleado);
console.log(this.trabajadores);
}
CambiarExterno(valor: boolean) {
this.trabajador_externo = valor;
}
}
