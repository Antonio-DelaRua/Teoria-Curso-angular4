 para instalar slim vamos a tener que utilizar composer,

 ahora lo que haremos es entrar en el directio de /www/curso-angular4-backend:

 creamos un nuevo fichero que lo llamaremos composer.json:

 {
  "require" :{
      "slim/slim": "2.*"
  },
  "autoload": {
      "classmap": ["piramide-uploader"]
  }

}

ahora buscamos  piramide-uploader-master en google y nos la bajamos y añadimos a nuestra carpeta curso-angular4-backend


ahora tenemos que entrar al directorio curso-angular4-backend y lanzamos el comando : 

composer install

