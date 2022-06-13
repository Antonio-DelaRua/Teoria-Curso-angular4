

ver los tipos de datos y las variables podemos definir diferentes tipos de datos :

public nombre = 'Antonio Delarua';    dentro de fruta.component.ts

{{nombre}}   dentro de fruta.component.html

yo puedo decirle a este dato que tipo de informacion va a guardar esta variable :

public nombre:string = 'Antonio Delarua';
public edad:number = 35;
public mayorDeedad: boolean = true;
public trabajos:Array<string> = ['carpintero','albañil','Fontanero'];

cuando creamos una arraid le tenemos que poner el string para determinarla.


Si la array es de letras pondremos string , si queremos que sea mixta de numeros , y nombres o cadena de texto pondremos <any> 