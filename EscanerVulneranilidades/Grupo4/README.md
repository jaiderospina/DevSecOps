# Integrantes

- **Paola Lara**
- **Yaneth Rodriguez**
- **Maria Mahecha**
- **Gustavo Ladino**

Realizamos dentro de Docker desktop montamos la aplicación en la maquina física, abrimos el link de la guía https://greenbone.github.io/docs/latest/22.4/container/index.html 
Debido a que vamos a realizar el trabajo directamente en Docker Desktop, nos dirigimos a llamar los servicios con Docker Compose File.
Realizamos la creación de una Carpeta Local. Dentro de esta creamos un archivo  Docker-compose.yml  
Ruta
C:\Users\maria\OneDrive\Documentos\Greenbone

![image](https://github.com/user-attachments/assets/a40f1bd8-6fae-4cf9-b332-14b52d8cca08)

Abrimos el archivo con un editor de Texto (Visual Studio Code)  y copiamos el código entregado en la guía 

![image](https://github.com/user-attachments/assets/2839bd8b-5551-41df-b44f-e042e6818714)

Realizamos la configuración del contenedor con el Greenbone community. Ejecutamos Windows PowerShell Como administrador, nos ubicamos en la carpeta Local creada y dentro de ubicación pegamos el código entregado en la guía 

![image](https://github.com/user-attachments/assets/a31ea500-bb52-4c6b-aae9-a8a3c41202fc)

En este paso realizamos que el Docker compose se ejecute  Docker compose yml adicional a este ejecutamos greenbone community pull donde se descarga las imágenes que utilizamos para construir

![image](https://github.com/user-attachments/assets/f21b4a01-dea4-4e68-844c-dafff786376d)

Siguiendo los pasos de la guía realizaremos la creación de las imágenes descargadas con el comando  up

![image](https://github.com/user-attachments/assets/5f98228b-eaf7-41b1-bd18-53184314bd5f)

Nota: En Caso de algún fallo al cargar un Volumen Utilizaríamos el siguiente código para validar los Logs de estos: (docker compose -f docker-compose.yml -p greenbone-community-edition logs -f)
Realizamos la configuración del Usuario administrador para realizar la sincronización  entre Docker Compose el archivo yml y greenbone, lo cual configuramos un contraseña y realizamos Logon en la IP indicada  http://127.0.0.1:9392/


![imagen](https://github.com/user-attachments/assets/b72bd4d8-731c-4416-9576-0ea5b9ea88a1)

Subimos la aplicación Greenbonepara visualizar contenedores y Visualizar las vulnerabilidades de este contenedor.

![imagen](https://github.com/user-attachments/assets/86a4919f-63ed-4950-893f-1d0a4822f24c)

Realizamos la validación dentro de Docker Desktop la creación del contenedor 

![imagen](https://github.com/user-attachments/assets/0bbaa27b-f566-4e1f-a5e4-cab6bb0537ab)

Validamos la Versión del Greenbone y no es necesario realizar la actualización

![imagen](https://github.com/user-attachments/assets/eaa1ca75-4a20-4577-95c3-eafa500a947b)

Dentro de Docker hub descargamos un contenedor dentro de imágenes para poder escanear las vulnerabilidades existentes 

![imagen](https://github.com/user-attachments/assets/fa7475ff-2277-46ef-9ea1-b978f881977e)

docker pull alpine:3.19.2

![image](https://github.com/user-attachments/assets/c66a10fe-0674-424b-8be8-79f1f09e1940)

Realizamos la descarga dentro de PowerShell para guardarla dentro de la máquina y poder escanearla en la aplicación Greenbone

![image](https://github.com/user-attachments/assets/da542334-00b1-4e6f-827f-a73da677683d)

Para crear la tarea de escaneo de Vulnerabilidades realizamos primero  la creación de un Targets donde configuramos el Nombre y la IP para inicio del escaneo 

![image](https://github.com/user-attachments/assets/41833a10-5b0f-4ddb-940d-f117f715fb9e)

![image](https://github.com/user-attachments/assets/cd17d0a3-d653-45bf-a5f9-421cd0332c09)

Se crea una tare donde se configura que escanee el Target anteriormente creado. Los demás campos los dejamos por defecto y empezamos a realizar el escaneo de esta 

![image](https://github.com/user-attachments/assets/eac6cdc0-c0c4-4732-803c-a47106464c3f)



















