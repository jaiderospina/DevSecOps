# Taller de Docker - Grupo 6

## Mienbros
##### * Erick Rommel Celis
##### * Diego Sinsicue

## Objetivo
Crear un contenedor de Docker con un servidor web Apache que utilice una carpeta local para almacenar los archivos del servidor. Asignarle una IP válida en la LAN y documentar cada paso del proceso.

---

## Imagenes
### Muestra 1

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo6/Imagen1.png)
### Muestra 2

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo6/Imagen2.png)
### Muestra 3
![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo6/Imagen3.png)

### Muestra 4
![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo6/Imagen4.png)

## Paso 1: Configuración inicial del contenedor

### 1. Crear una carpeta en local para los archivos web
Creamos una carpeta en el sistema local que será utilizada para almacenar los archivos del servidor Apache en el contenedor.

Comando utilizado:
```bash
mkdir -p ~/ApacheWebContent
```
### 2 crear el archivo html con su contenido
creamos el archivo html en la carpeta local creada 
Comando utilizado:
```bash
nano ~/ApacheWebContent/index.html
```

Se nos abrira una ventana emergente donde podemos agegar o editar la informacion del HTML

## Paso 2: Subir la imagen a Docker Hub

### 1. Iniciar sesión en Docker Hub
Iniciamos sesión en Docker Hub para poder subir la imagen.

Comando utilizado:
```bash
docker login
```

## Paso 3: Configuración de la red y asignación de IP

Si se requiere una IP específica en la LAN, podemos crear una red personalizada en Docker y asignarle una IP al contenedor para que sea accesible en la red local.

### 1. Crear una red personalizada en Docker
Creamos una red personalizada en Docker con un rango de IP específico.

Comando utilizado:
```bash
docker network create --subnet=192.168.1.0/24 mynetwork
```

## Paso 4: Crear y correr el Docker con Apache

subiremos y crearemos el docker con las caractetisticas

Comando utilizado:
```bash
docker run -d --name apache-container -p 8080:80 -v ~/ApacheWebContent:/usr/local/apache2/htdocs httpd
```

## Paso Adicional
En caso de que el docker ya este creado lo correremos para visualizarlo

```bash
docker star apache-container
```



