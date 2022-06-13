ahora vamos a aprender a hacer peticiones http y ajax en nuestro servicio :

para eso vamos a utilizar una api rest generica :

JSONPlaceholder :

vamos a hacer peticiones por post y lo q vamos a hacer es poner esa lista de 100 elementos a nuestro proyecto:

lo primero que hacemos es copiar la url de la web de la lista de jasonplaceholder:


en peticiones.service.ts:


@Injectable()
export class PeticionesService{
    public url:string;

 constructor(private _http:HttpClient){
    this.url = "https://jsonplaceholder.typicode.com/posts";
 }   


 esta seria la url de los post .


 vamos a definir un metodo, que va hacer una peticion por get a esa url q tenemos configurada :

 getArticulos(){
  return this._http.get(this.url)
  
}

ahora solo quedaria utilizar este metodo dentro de un componente vamos a nuestros coches.component.ts y en el Oninit :

ngOnInit(){
     this._peticionesService.getArticulos().subscribe (
         result =>{
             this.articulos = result;
             if(!this.articulos){
                 console.log("error en el servidor");
             }

         },
         error => {
             var errorMessage = <any>error;
             console.log(errorMessage);
         }
     )

    }

añadimos la clase : 
public articulos :

export class CochesComponent{
    public coche: Coche;
    public coches:Array<Coche>;
    public articulos:any;


ahora lo que vamos a hacer es mostrar el listado de articulos en nuestra pag :

vamos a coches.component.html :
 ya que estamos vamos a definir el estilo tambien por separado : 


quedaria asi :

<h1>Componente de coche</h1>




<style>
   div {
      float: left;
   }

   .listado {
      margin-left: 30px;

   }

   form {
      width: 200px;

   }

   input[type="text"],
   span {
      display: block;
      width: 100%;
   }
</style>

/div>

<div class="listado">
   <h3>Listado de coches</h3>

   <ul>
      <li *ngFor='let coche of coches'>
         {{coche.nombre}}--{{coche.caballaje}}--{{coche.color}}
      </li>
   </ul>

</div>

<div class="listado">
<h3>Listado de articulos</h3>
<ul>
<li *ngFor="let articulo of articulos">
       {{articulo.id}}  - {{articulo.title}}
</li>

</ul>


</div>





