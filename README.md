# TAREA
1: Crear un contenedor con Docker-MySQL y persistir la información

PASOS PARA CREAR UN CONTENEDOR EN DOCKER 

//docker run --name mysql-container -e MYSQL-ROOT-PASSWORD=tu-contraseña -e MYSQL-DATABASE=mi-base-datos -v mysql-data:/var/lib/mysql -d mysql : latest

// perejar ps

//docker exec -it mysql-container mysql -uroot -p


Ejercicio 2: Dockers el servicio de MySQL
Paso 1: Crear un archivo docker-compose.yml


////////////////////////////////////////////////////////////////////////////////////////////
versión: '3.8'
servicios:
  mysql:
    imagen: mysql: :último
    contenedor-name: mysql-container
    medio ambiente:
      MYSQL-ROOT-PASSWORD: tu-contraseña
      MYSQL-DATABASE: mi-base.datos
    volúmenes:
      - mysql-data:/var/lib/mysql
    puertos:
      - "3306:3306"
volúmenes:
  missql-data:
////////////////////////////////////////////////////////////////////////////////////////////////


//el perdedor-compose up -d


//odador-compose ps


//el peremeador-compose abajo


//el perdedor-compose up -d





Ejercicio 3: Usar MySQL con Docker y Docker Compose

Creación de una Aplicación Node.js
Paso 1: Crear el proyecto Node.js
Inicia un proyecto Node.js:

////////////////////////////////////////////////
mkdir docker-mysql-node
cd docker-mysql-node
npm init -y
////////////////////////////////////////


/////npm instalar mysql2 express



////////////////////////////////////////////////////////////////////////////////

const express = require('express');
con mysql = require('mysql2');

aplicación const = express();
conste oporto = 3000;

// Conexión a la base de datos
const db = mysql.createConnection(
  anfitrión: 'localhost', // Cambiar si se estás usando un contenedor separado
  usuario: 'root',
  contraseña: 'tu-contraseña',
  base de datos: 'mi-base.datos',
-);

db.connect((err) =
  si (err)
    console.error ('Error conectando a la base de datos:', err);
  Si no,
    console.log('Conectado a MySQL');
  -
-);

app.get('/', (req, res) =
  db.query('SELECT AHORA() AS fecha', (err, results) =
    si (err)
      res.status(500).send ('Erro se reeca la consulta');
    Si no,
      res.json (resultados);
    -
  -);
-);

app.escuchar(port, () =
  console.log( `Servidor escuchando en http://localhost:$.port?`);
-);


////////////////////////////////////////////////////////////////////////////////



//el perdedor-compose up -d



//nodo index.js

// http://localhost:3000
