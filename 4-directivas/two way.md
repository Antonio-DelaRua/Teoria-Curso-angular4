lo primero vamos a ir al app.module.ts y vamos a importar el forms:
import { FormsModule } from '@angular/forms';
 imports: [
    FormsModule,

<h3>Selector de colores</h3>
<input type="text" />
<div [ngStyle]="{background:color, 'width': '200px', 'height': '200px', 'float': 'right', 'margin-right':'78%'}"></div>
<div stryle="clear:both"></div>

depues creamos la etiqueta
public color_seleccionado:string;

this.color_seleccionado = '#ccc';
siguiente paso:

<div>
<h3>Selector de colores</h3>
<input type="text" [(ngModel)] ='color_seleccionado'/>
<pre>
    <strong>Color Elegido</strong>
    {{color_seleccionado}}
</pre>
<div [ngStyle]="{background:color_seleccionado, 'width': '200px', 'height': '200px', 'float': 'right', 'margin-right':'78%'}"></div>
<div style="clear:both"></div>

</div>


le podemos poner un boton para que nos muestre en el log el color

<button (click)="logColorSeleccionado">Mostrar Log</button>

le ponemos tb para que nos muestre un texto del color con un pre :

<pre>
    <strong>Color Elegido</strong>
    {{color_seleccionado}}
</pre>

despues nos vamos a la carpeta de component.ts 
logColorSeleccionado(){
    console.log(this.color_seleccionado);
  }
