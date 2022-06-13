lo primero vamos a crear una propiedad en nuestro componente que se va a llamar :

public fecha;

despues le damos un valor en el constructor:

this.fecha = new Date();

le podemos indicar una fecha en concreto:

(2017, 4, 10)

para mostrar nuestra fecha vamos al archivo html:

y con las 2 llaves :  {{fecha}}

la metemos dentro de un br: 

<br/>
    {{fecha}}
<br/>

asi tenemos la fecha completa sin ningun tipo de procesamiento

por lo cual vamos a utilizar una pipe :

<br/>
    {{fecha| date:''}}
<br/>

asi ya nos lo cambiara un poco ya le  hemos injectado el pipe | date:''

tambien le podemos indicar el mes el dia y el año :

<br/>
    {{fecha| date:'dd/MM/yy'}}   o     {{fecha| date:'dd/MM/yyyy'}} 
<br/>

si queremos decorarlo un poco mas 
<br/>
  {{fecha| date:'dd/MM/yyyy'}}
  {{fecha| date:'fullDate'}}
<br/>







