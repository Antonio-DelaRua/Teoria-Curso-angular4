

para hacer un ngif:

export class Empleadocomponent
le damos un valor aquí :
public trabajador_externo:boolean;

despues le damos un valor en el constructor:

this.trabajador_externo = false;

continuamos iendonos a la carpeta .html y modificamos según sea nuestra preferencia ej:

<ul *ngIf="trabajador_externo == true">
<li>{{trabajadores[0].nombre}}</li>
<li>{{trabajadores[0].edad}}</li>
<li>{{trabajadores[0].cargo}}</li>
<li>{{trabajadores[0].contratado}}</li>
</ul>
<ul *ngIf="trabajador_externo == false">
<li>{{empleado.nombre}}</li>
<li>{{empleado.edad}}</li>
<li>{{empleado.cargo}}</li>
<li>{{empleado.contratado}}</li>
</ul>