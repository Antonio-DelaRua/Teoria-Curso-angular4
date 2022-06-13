  

vamos a utilizar una variable app y el metodo post, haremos una nueva ruta y le vamos a pasar un id , vamos a tener una fuccion que va a tener como parametro id y vamos a tener una fuccion que va a recoger como parametros id y vamos a usar dentro de este metodo db y app para recoger cosas del api rest.

haremos una variable json y vamos a recoger la variable que nos lleva por post llamada json.

creamos una variable data que vamos a decodificar y la variable json vamos a convertirla en un objeto.

lo siguiente sera hacer una query sql update de la tabla productos SET y vamos a darle un valor a cada uno de los campos de la tabla. 

despues hacemos la query en si y le pasamos la sql para ejecutar, 

entonces si el resultado es positivo vamos a devolver un json

// ACTUALIZAR EL PRODUCTO

$app->post('/update-producto/:id', function($id) use($db, $app){
  $json = $app->request->post('json');
   $data = json_decode($json, true);


  $sql = "UPDATE productos SET ". 
      "nombre = '{$data["nombre"]}', ".
      "descripcion = '{$data["descripcion"]}',".  
      "precio = '{$data["precio"]}' WHERE id = {$id}";  

   $query = $db->query($sql);

   if($query){
       $result = array(

           'status' => 'success',
           'code'  => 200,
           'message' => 'el producto se ha actualizado correctamente'
       );
       
   }else{
       $result = array(
        'status' => 'error',
        'code' => 404,
        'message' => 'el producto no se ha actualizado correctamente'   
       );
   }

   echo json_encode($result);
});