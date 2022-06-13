

es el primer metodo que se lanza al instanciar un objeto o una clase, cuando nosotros llamemos al componente lo primero que se va a iniciar es el constructor. Se utiliza para inizializar las propiades de la clase, asignarle el valor a las propiedades.

constructor(){

}

podriamos hacer console.log de lo que quisieramos y veriamos el resultado in situ en el navegador.

constructor(){
console.log(this.comodin),
console.log(this.trabajos)

}
            tb podemos ponerlo asi :


constructor(){
this.nombre = 'Antonio Delarua';
this.edad = 35;
this.mayorDeedad= true;
this.comodin = true;

}

como definimos una funcion dentro de una clase de typescript y dentro de una clase de comoponente: 

constructor(){
this.nombre = 'Antonio Delarua';
this.edad = 35;
this.mayorDeedad= true;
this.comodin = true;
this.holaMundo(this.nombre);

}

holaMundo(nombre:string){
alert('Hola Mundo!!' + nombre);
}

para llamar metodo y hacer ciertas funcionalidades nada mas cargar un componente tenemos el ngOninit:
constructor() {
this.nombre = 'Antonio Delarua';
this.edad = 35;
this.mayorDeedad = true;
this.comodin = true;
}
ngOnInit() {
this.CambiarNombre();
this.cambiarEdad();
alert(this.nombre + '' + this.edad);
}

CambiarNombre() {
this.nombre = 'danny';
}
cambiarEdad() {
this.edad = 35;
}
