

el primer metodo que vamos a crear va a ser un metodo POST que nos va a permitir guardar un nuevo producto en la base de datos.

vamos a utilizar el metodo post : 

en nuestro index.php:

$app->post('/productos', fuction() use($app, $db){
  $json = $app->request->post('json');
  $data = json_decode($json, true);            <---- para decodificar el valor que tenga la variable json    >

  var_dump($json);
  var_dump($data);

});

aqui hemos hecho una variable con POST que va a llevar un json con unos datos y luego lo vamos a mostrar por aqui.

ahora volvemos a Postman :

y señalamos Body :

y elegimos x-www-form-urlencoded (X)

para simular un formulario real y normal vamos a pasarle un parametro por POST de acuerdo a una variable.

dentro de value vamos a poner : 

{"nombre","ordenador","precio":200}

le damos a send y Magic !!***********!!!

siguiente paso vamos a hacer una query a nuestra base de datos  en index.php:



if(!isset($data['imagen'])){

data['imagen']=null;
}



$query = "INSERT INTO productos VALUES(NULL,".
      "'{$data[ 'nombre']}',".
      "'{$data[ 'descripcion']}',".
      "'{$data[ 'precio']}',".
      "'{$data[ 'imagen']}'".
     ")";



ahora le ponemos un var_dump para probarla en Postman:

if(!isset($data['imagen'])){

data['imagen']=null;
}



$query = "INSERT INTO productos VALUES(NULL,".
      "'{$data[ 'nombre']}',".
      "'{$data[ 'descripcion']}',".
      "'{$data[ 'precio']}',".
      "'{$data[ 'imagen']}'".
     ")";


     var_dum($query);



nos dara error porq nos queda poner :


if(!isset($data['nombre'])){

data['nombre']=null;
}

if(!isset($data['descripcion'])){

data['precio']=null;
}

if(!isset($data['imagen'])){

data['imagen']=null;
}

if(!isset($data['imagen'])){

data['imagen']=null;
}


$query = "INSERT INTO productos VALUES(NULL,".
      "'{$data[ 'nombre']}',".
      "'{$data[ 'descripcion']}',".
      "'{$data[ 'precio']}',".
      "'{$data[ 'imagen']}'".
     ")";


     var_dum($query);


//////////////////////////////solucionado////////////////////////////////


ahora vamos a utilizar mysqli para ejecutar esta consulta sql en nuestro mysqli vamos a crear una variable insert:

$insert = $db->query($query);

 $result = array(
        'status' => 'error',
        'code' => 404,
        'message' => 'Producto NO SE A creado correctamente'
    );

if ($insert){

    $result = array(
        'status' => 'success',
        'code' => 200,
        'message' => 'Producto creado correctamente'
    );
}
luego en el Postman podemos crear nuevos productos a nuestra base de datos con el value.


asi quedaria nuestro index.php:


<?php

require_once "vendor/autoload.php";

$app = new \Slim\Slim();

$db = new mysqli('localhost', 'root','', 'curso-angular4');
   
$app->get("/pruebas", function() use($app, $db){
           echo "hola mundo desde Slim";
});

$app->get("/pobando", function() use($app){
    echo "hola mundo ";
});


       
$app->post('/productos', function() use($app, $db){
  $json = $app->request->post('json');
  $data = json_decode($json, true);

    if(!isset($data['nombre'])){

    $data['nombre']=null;
    }
    
    if(!isset($data['descripcion'])){
    
    $data['precio']=null;
    }
    
    if(!isset($data['imagen'])){
    
    $data['imagen']=null;
    }
    
    if(!isset($data['imagen'])){
    
    $data['imagen']=null;
    }

     
   $query = "INSERT INTO productos VALUES(NULL,".
   "'{$data[ 'nombre']}',".
   "'{$data[ 'descripcion']}',".
   "'{$data[ 'precio']}',".
   "'{$data[ 'imagen']}'".
  ")";

  $insert = $db->query($query);

  $result = array (
    'status' => 'error',
    'code' => 404,
    'message' => 'Producto NO creado correctamente'
  ); 
 

if($insert){
  $result = array (
    'status' => 'success',
    'code' => 200,
    'message' => 'Producto creado correctamente'
  );
}

echo json_encode($result);

});

$app->run();


