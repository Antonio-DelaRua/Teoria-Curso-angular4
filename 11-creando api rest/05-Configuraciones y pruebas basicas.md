para empezar a crear nuestra api rest con php y empezar a utilizar nuestro framework lo primero que tenemos que hacer crearnos un 

index.php que va a ser el fichero principal de la api rest, en este fichero lo que tenemos que hacer es importar o incluir el autoload.php:


index.php :

<?php

require_once "vendor/autoload.php";

$app = new \Slim\Slim();
   
$app->get("/pruebas", function() use($app){
           echo "hola mundo desde Slim";

});

$app->run();

ahora si nos vamos a nuestro localhots y ponemos : 

localhost/curso-angular4-backend/index.php/prueba  

nos aparece nuestro hola mundo .

si en vez de pruebas ponemos otro nombre ese seria el que necesitariamos para entrar .


