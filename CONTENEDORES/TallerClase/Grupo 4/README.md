# Taller  de clases contenedor
### Integrantes:
- **Yaneth Rodríguez**
- **Paola Lara**
- **Gustavo Ladino**
- **Maria Mahecha**

## Explicacion taller Docker

- **Paso 1**  
**Se realiza la explicación del paso a paso realizando el Taller en Docker Desktop
Creamos una carpeta en una maquina local donde guardarás los archivos web. Este será el volumen que montarás en los contenedores de Apache**

mkdir C:\mi_proyecto_apache

cd C:\mi_proyecto_apache


![image](https://github.com/user-attachments/assets/a8cee9af-6ac2-4a77-a8e3-7336a815a54e)


**Paso2**

Creamos un archivo llamado Dockerfile con el siguiente contenido. Este archivo define el contenedor que instalará Apache y mapeará una carpeta local

![image](https://github.com/user-attachments/assets/ecb2b0cb-63f4-49f0-97c1-b0271b6ed38f)


![image](https://github.com/user-attachments/assets/b7e14636-9ee8-48ad-9a08-cb8fe10b2f42)

Este Dockerfile realiza lo siguiente:
•	Usa la imagen oficial de Apache.
•	Copia los archivos de un sitio web desde la carpeta local mi_sitio_web al contenedor (en la ruta donde Apache espera los archivos).
•	Expone el puerto 80 para acceder al servidor web desde fuera del contenedor


**Paso 3**

Crear la carpeta con los archivos del sitio web
Dentro de C:\mi_proyecto_apache, crea la carpeta mi_sitio_web donde guardarás tus archivos HTML y otros recursos del servidor web.

mkdir mi_sitio_web

![image](https://github.com/user-attachments/assets/e6a48a26-e943-4e25-bd61-a5ab447b13dc)

![image](https://github.com/user-attachments/assets/332fb75a-1e03-4b2b-a2fc-28f22f46609c)

Creamos un archivo index.html con contenido  para que el servidor Apache sirva una página web.

**Paso 4**
Construir la imagen con Docker
Desde el directorio C:\mi_proyecto_apache, ejecuta el siguiente comando en PowerShell para construir la imagen.
docker build -t mi_apache_web .

![image](https://github.com/user-attachments/assets/d9064b2b-ab75-4b57-af29-9cad40e4e710)

**paso 5**
Crear una red Docker personalizada
Para asignar IPs fijas a los contenedores, necesitamos crear una red personalizada en Docker. Esto se hace para garantizar que ambos contenedores estén en el mismo segmento de red.
docker network create --subnet=192.168.2.0/24 mi_red_lan
Esta red personalizada tiene el rango de IPs de 192.168.2.0 a 192.168.1.255.

![image](https://github.com/user-attachments/assets/b13dc113-7cad-40c8-ad9d-8bde488e3486)








