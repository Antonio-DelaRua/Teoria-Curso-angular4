AHORA vamos a crear un metodo que nos permita sacar un solo producto de la base de datos es decir que nosotros por la url de postman le vamos a pasar una ide de un producto y nos va a sacar el producto correspondiente :

//DEVOLVER UN SOLO PRODUCTO:

$app->get('producto/:id', function($id) use($db, $app)){

    $sql = 'SELECT * FROM productos WHERE id = '$id;
    $query = $db->query($sql);
   
    $result = array(
        'status' => 'error',
        'code'   => 404,
        'message' => 'producto no disponible'
    ); 

    if($query->num_rows == 1){
        $producto = $query->fetch_assoc();
        'status' => 'succes',
        'code'   => 200,
        'data' => $producto
    }
    
    echo json_encode($result);
});

