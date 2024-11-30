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







