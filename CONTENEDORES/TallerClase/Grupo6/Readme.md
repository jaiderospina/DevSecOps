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

## Paso 4: Evidencia de los commits de todos los miembros del equipo

Para cumplir con el requisito del taller de evidenciar los commits de todos los miembros del equipo, cada persona debe realizar al menos un commit en el repositorio de Git. Cada miembro puede añadir una pequeña contribución, como la subida de capturas de pantalla o la edición de algún archivo en la documentación, y realizar un commit con su nombre y una breve descripción de lo que realizó.

### Procedimiento para realizar un commit

1. **Agregar los cambios**: Cada miembro debe asegurarse de que los cambios que realizó están listos para ser enviados al repositorio.
   
   Comando utilizado:
   ```bash
   git add .
```




