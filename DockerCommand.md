

https://hub.docker.com/


#Comandos genericos

    docker pull NOMBREIMAGEN . Este comando sirve para descargar una imagen 
    docker image ls .lista  las imagenes
    docker run --name   NOMBRECONTENEDOR -e POSTGRES_PASSWORD=mysecretpassword -d NOMBREIMAGEN 
    docker run --name DB-postgres -e POSTGRES_PASSWORD=masterdb -d postgres
    docker images  muestra imágenes que tenemos descargadas
    docker ps -a    muestra que contenedores estan funcionando
    docker rmi  IMAGE_ID
    docker info  Muestra informacion de las imagenes, tamaño , fecha creacion  nombre ,…
    docker search NAME   para buscar in docker
    docker inspect <friendly-name|container-id> . para saber acerca del contenedor
    docker logs <friendly-name|container-id>
    docker exec -it <friendly-name|container-id> sh  comando dentro del contenedor 

#Comandos para el contenedor

    docker start
    docker stop
    docker kill
    docker rm

#Docker composer

    docker-compose up -d  // Levantar la maquina con un fichero docker-compose  hay que entrar en la carpeta donde este el fichero
    docker-compose down