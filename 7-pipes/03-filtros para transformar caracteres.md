para que el texto sea en mayusculas lo podemos utilizar con una pipe que se llama :

 {{fecha| date:'fullDate'| uppercase}}     (para convertirlo en mayuscula)

 puedo ir encadenando las diferentes pipes una detras de otra para que vaya procesando una variable como nos interesa:
 para ponerlo todo en minuscula :

  {{fecha| date:'fullDate' | uppercase | lowercase}}

tambien podemos hacer una prueba creando una propiedad nueva : en home.component.ts

public nombre = "Antonio DelaRua Fernandez"

ahora si queremos procesar ese texto de una manera en concreta nos vamos a home.component.html:

{{nombre}} podemos dividir los textos con - :

<br/>
  {{fecha| date:'dd/MM/yyyy'}}

-

  {{fecha| date:'fullDate' | uppercase | lowercase}}

-

  {{nombre | lowercase}}

<br/>

y de esta forma utilizariamos las pipe para convertir un texto de minuscula a mayuscula y al reves =)