Cabeceras HTTP en PHP para permitir el acceso CORS con Apache o con otro servidor web.

En este caso te pongo las cabeceras configuradas en PHP para que puedas utilizarlo en los desarrollos de tus APIs REST o cualquier proyecto que tengas:




header('Access-Control-Allow-Origin: *');
header("Access-Control-Allow-Headers: X-API-KEY, Origin, X-Requested-With, Content-Type, Accept, Access-Control-Request-Method");
header("Access-Control-Allow-Methods: GET, POST, OPTIONS, PUT, DELETE");
header("Allow: GET, POST, OPTIONS, PUT, DELETE");
$method = $_SERVER['REQUEST_METHOD'];
if($method == "OPTIONS") {
    die();
}





lo copiamos en nuestro codigo index.php justo debajo de $db

//////////////Con estas cabeceras no tendremos problemas con el CORS////////
