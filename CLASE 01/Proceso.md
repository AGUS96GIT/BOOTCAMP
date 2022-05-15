1. Hacemos pull (descargamos) de la imagen de apache 

    docker pull httpd:latest

2. en el directorio de docker, creamos un dockerfile

    cd .docker/
    nano dockerfile

3. Establecemos la conexión con la imagen apache:

    FROM httpd:latest 

3.  montamos nuestra imagen en local con la imagen descargada, nombre ("imagenapache")"

    docker build -t imagenapache:latest .

4  para lanzar el contenedor usamos el comando run para desplegarlo en nuestra máquina

    docker run -p 8080:80 primeraimagen:latest

En el navegador ponemos nuestra ip:8080 y nos abrirá el index.html


5 Creacion de un volumen:

  docker volume create volumenuno

6 Levantamos el volumen en la imagen para compartirla (tenemos que pasar el contenedor antes, haciendo un stop):

  docker run -v volumenuno:/opt/data -p8080:80 imagenapache:latest

7 abrir una terminal de comandos dentro del contenedor:

  docker exec -it idcontainer bash
