

para simplificar las cosas y no tener problemas de configuracion con el apache y locales vamos a utilizar el metodo GET y POST, la ruta se va a llamar delete-producto le vamos a pasar tambien un id como parametro, vamos a tener una fuccion de calvcan con  un id, vamos a usar las variables db y app dentro de la funcion de calvan.

despues vamos a hacer una consulta sql y le concatenamos el id que nos lleva por el parametro.

entonces vamos a lanzar esa sql vamos a crear una variable query, como hay sqli ($db)->query() le pasamos nuestro sql

le ponemos la array

y sino que nos devuelva un error

Y PARA Que nos devuelva un resultado en json


$app->get('/delete-producto/:id', function($id) use($db, $app){
    $sql = 'DELETE FORM productos WHERE id = .id';
    $query = $db->query($sql);

    if($query){
        $result = array(

        'status' => 'succes',
        'code'   => 200,
        'message' => "el producto se ha elimidado correctamente"
        );
    }else{
         $result = array(

        'status' => 'error',
        'code'   => 404,
        'message' => "el producto NO se ha elimidado correctamente"
        );
    }

      echo json_encode($result)

});

