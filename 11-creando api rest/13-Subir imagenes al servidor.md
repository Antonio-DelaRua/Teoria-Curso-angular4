

Vamos a utilizar un metodo post app post , y se va a llamar la ruta upload-file vamos a determinarle una funcion y que va a usar db app.



// SUBIR UNA IMAGEN A UN PRODUCTO

$app->post('/upload-file', function() use($db, $app){
  $result = array(
      'status'  => 'error',
      'code' => 404,
      'message'=> 'el archivo no a podido subirse'
  );

  if(isset($_FILES['uploads'])){
//echo "LLegan los datos"   -------hacemos la prueba en post que todo llegue correctamente
  $piramideUploader = new PiramideUploader();

  $upload = $piramideUploader->upload('image', "uploads", "uploads", array('image/jpeg', 'image/png', 'image/gif'));
  $file = $piramideUploader->getInfoFile();
  $file_name = $file['complete_name'];

  if(isset($upload) && $upload["uploaded"] == false){
    $result = array(
      'status' => 'error',
      'code' => 404,
      'message' => 'el archivo no a podido subirse'   
     );

  }else{
    $result = array(

      'status' => 'success',
      'code'  => 200,
      'message' => 'el producto se ha subido'
    );
  }
  
}

  echo json_encode($result);
});