# Crear un servidor de MYSQL mediante un contenedor de Docker

### 1. Descargar la imagen de MYSQL desde Docker Hub

```
docker pull mysql:8.4.8
```

### 2. Verificar y filtrar imágenes de Docker

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