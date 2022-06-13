- vamos a empleado.component y vamos a añadir  una propiedad q se va a llamar color :
- public color:string;
- despues ponemos la etiqueta 
- this.color ='red';

<h3>Colores switch</h3>
<ul [ngSwitch]="color">
    <li *ngSwitchCase="'red'" [ngStyle]="{background:color, 'color': 'white', 'padding': '20px'}">es de color rojo</li>
    <li *ngSwitchCase="'green'" [ngStyle]="{background:color, 'color': 'white', 'padding': '20px'}">es de color verde</li>
    <li *ngSwitchCase="'blue'" [ngStyle]="{background:color, 'color': 'white', 'padding': '20px'}">es de color azul</li>
</ul>

ya con este listado solo tenemos q cambiarle el color desde la etiqueta 
this.color ='red';   ej: this.color ='green';