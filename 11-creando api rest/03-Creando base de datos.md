vamos a crear una base de datos para importarla en phpmyadmin:

hemos creado una carpeta curso-angular4-backend dentro creamos un fichero bbdd.sql:

CREATE DATABASE IF NOT EXISTS developer;
USE developer;

CREATE TABLE productos(
id int(255) auto_increment not null,
nombre varchar(255),
description text,
precio varchar(255),
imagen varchar(255),
CONSTRAINT pk_productos PRIMARY KEY(id)
)ENGINE=InnoDb;

ahora vamos a nuestro phpmyadmin y importamos nuestro bbdd.sql 