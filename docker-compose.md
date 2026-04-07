# Docker Compose Commands

### 1. Para ejecutar un docker-compose.yml

```
docker-compose up -d
docker compose up -d
```

### 2. Para eliminar todo lo levantado por el compose

```
docker compose down
```


### 3. Para listar y filtrar servicios levantados por docker compose

```
docker compose ps
docker compose ps -a (lista todos independiente de su status)
docker compose ps | grep my (mac/linux)
docker compose ps | findStr my (windows)
```

### 4. Para detener todos los servicios levantados por docker compose

```
docker-compose stop
```

### 5. Para detener un servicio específico

```
docker-compose stop mysql-service (name service)
```

### 6. Para arrancar todos los servicios creados o detenidos

```
docker-compose start
```

### 7. Para arrancar un servicio específico si está creado o detenido

```
docker-compose start mysql-service (name service)
```

### 8. Para crear y luego levantar un servicio específico en 2 pasos

```
docker-compose create mysql-service2 (name service)
docker-compose start mysql-service2 (name service)
```

### 9. Para crear y arrancar 1 o más servicios en (1 paso)

```
docker compose up -d mysql-service1 mysql-service2
```

### 10. Para eliminar un servicio específico

```
docker-compose rm -s mysql-service (por confirmación)
docker-compose rm -s -f mysql-service (eliminación inmediata)
```

### 11. Para eliminar 1 o más servicios

```
docker compose down mysql-service mysql-service2
```

### 12. Para lanzar un archivo compose con nombre personalizado

```
docker compose docker-compose.env.yml up -d
```

### 13. Para obtener el archivo compose desde la terminal

```
docker compose config (si tiene nombre nativo: compose ó docker-compose)
docker compose -f docker-compose.env.yml config (nombre personalizado)
```

### 14. Para lanzar un archivo compose con una configuración específica de entorno diferente al .env

```
docker compose --env-file .env.dev -f docker-compose.health.yml up -d
```

### 14. Permite bajar todos los servicios incluyendo sus volúmenes

```
docker compose down -v
```

### 15. Para crear mi imagen personalizada sin nombre

```
docker build .
```