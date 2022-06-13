

como nos conectamos a una base de datos en php ?


creamos una variable que se va a llamar :

$db = mysqli('localhost', 'root','', 'curso-angular4');   |||| (1 servidor 2usuario base de datos 3contraseña4nombre de la base de datos)
   
$app->get("/pruebas", function() use($app, $db){             <----------------- ACUERDENSE DE PONERLO AQUI TAMBIEN>
           echo "hola mundo desde Slim";
           var_dump($db);


vamos al Postman y podemos ver el cambio.

