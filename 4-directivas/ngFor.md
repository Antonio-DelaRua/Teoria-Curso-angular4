<h3 style="color:blue;">
    {{titulo}}
</h3>



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

<h3>Listado de empleados</h3>

<ul>
    <li *ngFor="let empleado of trabajadores; let i =index">
     <strong>   empleado {{i+1}} </strong>
    <ul>
        <li>{{empleado.nombre}}</li>
        <li>{{empleado.edad}}</li>
        <li>{{empleado.cargo}}</li>
        <li *ngIf="empleado.contratado == true">Esta contratado</li>
        <li *ngIf="empleado.contratado == false">No esta contratado</li>

    </ul>

    </li>


</ul>