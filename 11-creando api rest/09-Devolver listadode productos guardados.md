ahora vamos a crear un metodo que se encarge de listar nuestros productos en la base de datos


tenemos el metodo en la ruta productos en la base de datos de nuestra tabla base en index.php






// LISTAR TODOS LOS PRODUCTOS

$app->get('/productos', function() use($db, $app){
       $sql = 'SELECT * FROM productos ORDER BY id DESC;    <---- sacar todo las filas de todos los productos y mostralo de forma descendete >
       $query = $db->query($ql);                            <----esto va a coger los resultados>

    //   var_dump($query->fetch_all());                     <---con el metodo fetch_all nos muestra el listado de productos en forma de array>

       while ($producto = $query->fetch_assoc()) {          <--- generar un array de objetos>

       $productos[] = $producto; 
       }
       $result = array(
        'status' => 'succes',
        'code' => 200.
        'data' => $productos
       );
})

y con esto ya tendriamos una ruta para listar todos los productos que tenemos guardados en la base de datos.









