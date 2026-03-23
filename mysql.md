# Crear un servidor de MYSQL mediante un contenedor de Docker

### 1. Descargar la imagen de MYSQL desde Docker Hub

```
docker pull mysql:8.4.8
```

### 2. Listar y filtrar imágenes de Docker

```
docker images (listar todas las imágenes disponibles)
docker images | grep mysql (linux/mac) -> filtrar
docker images | findStr mysql (windows) -> filtrar
```

### 3. Eliminar una imagen de Docker

```
docker rmi mysql:8.4.8 (nombre de la imagen)
docker rmi ff4a089dadda (ID) 
```

### 4. Crear un contenedor con la imagen de MYSQL descargada con nombre aleatorio

```
docker create mysql:8.4.8
```

### 4. Para eliminar un contenedor

```
docker rm sad_lalande (nombre)
docker rm 3f8233ea81d0d3006cb8a7587dd751c1f9166cc30a71d163339c7668142a23f7 (ID)
```

### 5. Crear un contenedor con nombre

```
docker create --name mysqlserver mysql:8.4.8
```

### 6. Listar contenedores de Docker

```
docker ps -a (Lista todos los contenedores independiente de su status)
docker ps (Lista solo los que estén en ejecución)
```

### 7. Filtrar contenedores de Docker

```
docker ps -a | grep my (linux/mac)
docker ps -a | findStr my (windows)
docker ps a | grep my (linux/mac)
docker ps a | findStr my (windows)
```

### 8. Para monitorear la salida del contenedor (logs)

```
docker logs mysqlserver (nombre)
docker logs 1ec1a4767b1137bbc5fe8dbdb87febf42fb316e04eaebf973cfafef68463d759 (ID)
Puedo aplicar logs si el contenedor está detenido o en ejecución
```

### 9. Crear y ejecutar un contenedor con variables de entorno en modo attached

```
docker run --name mysqlserver -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8
```

### 10. Crear y ejecutar un contenedor con variables de entorno en modo dettached

```
docker run -d --name mysqlserver -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8 (te habilita seguir trabajando con la consola)
```

### 11. Para detener un contenedor activo

```
docker stop mysqlserver (nombre)
docker stop 20f55b292d655fce6b8b19ab3571be6a3b2dd7fafd57a3782c39e10ccaa7133e (ID)
```

### 12. Para arrancar un contenedor detenido

```
docker start mysqlserver (nombre)
docker start 20f55b292d655fce6b8b19ab3571be6a3b2dd7fafd57a3782c39e10ccaa7133e (ID)
```

### 13. Para hacer una detención crítica

```
docker kill mysqlserver (nombre)
docker kill 20f55b292d655fce6b8b19ab3571be6a3b2dd7fafd57a3782c39e10ccaa7133e (ID)
Esto genera que recursos que la imagen ocupe puedan haber sido corrompidos
```

### 14. Para inspeccionar un contenedor

```
docker inspect mysqlserver (nombre)
docker inspect 20f55b292d655fce6b8b19ab3571be6a3b2dd7fafd57a3782c39e10ccaa7133e (ID)
```

### 15. Para ingresar a la red virtual de Docker desde windows

```
Anotar \\wsl$ en la barra de direcciones desde cualquier directorio
```

### 16. Para inspectar una imagen

```
docker image inspect mysql:8.4.8 (nombre)
docker image inspect 20f55b292d655fce6b8b19ab3571be6a3b2dd7fafd57a3782c39e10ccaa7133e (ID image)
```

### 16. Para crear un contenedor con un volumen anónimo

```
docker run -d --name mysqlserver -v /var/lib/mysql -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8
```

### 17. Para eliminar un contenedor que está en ejecución

```
docker rm -f mysqlserver (nombre) or ID
docker stop mysqlserver (nombre) or ID
docker rm mysqlserver (nombre) or ID
```

### 18. Para remover volúmenes huerfanos

```
docker volume prune
```

### 19. Para listar volúmenes

```
docker volume ls
```

### 20. Para filtar volúmenes

```
docker volume ls | grep my (nombre) (linux/mac)
docker volume ls | findStr my (nombre) (windows)
```

### 21. Para eliminar un contenedor con un volumen anónimo u otro

```
docker rm -fv mysqlserver (nombre) or ID
```

### 22. Para crear un contenedor con un volumen host

```
docker run -d --name mysqlserver -v E:\docker_examples\docker\volumes\mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8
```

### 23. Para eliminar el contenido de una carpeta de volumen host

```
rmdir /s /q E:\docker_examples\docker\volumes\mysql (windows)
rm -rf E:\docker_examples\docker\volumes\mysql (linux/mac)
```


### 24. Para crear un contenedor con un volumen nombrado 

```
docker run -d --name mysqlserver -v vol-mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8
```

### 25. Para identificar un contenedor con un volúmen TMPFS
```
docker run -d --name mysqlservertest -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_USER=user -e MYSQL_PASSWORD=123 -e MYSQL_DATABASE=sqldb mysql:8.4.8
Es una marca de volumen vacío para denotar que se puede manejar persistencia
```

