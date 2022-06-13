[style.border]=" color_seleccionado == 'red' ? '5px solid black : '1px solid green'"

dentro del <pre> por ejemplo podemos ponerlo
podemos poner otra calse como el fondo azul

[class.fondoAzul]="color_seleccionado == 'blue'" 

creamos una carpeta styles.css

y creamos la clase
.fondoAzul{
   background: lightblue !important;

}
podemos cambiar el tamaño de la letra

.letraGrande{
   font-size: 30px;
}

y en html

letraGrande: 1 == 1


lo podemos simplificar asi 
[ngClass]="[ 'fondoAzul', 'letraGrande']"