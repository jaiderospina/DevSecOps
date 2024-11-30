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

**Paso 6**

**Ejecutar los contenedores**
Ahora, creamos y ejecutamos dos contenedores basados en la imagen con direcciones IP dentro del segmento 192.168.2.0/24.


![image](https://github.com/user-attachments/assets/77edc52b-24f6-4957-9928-acf0d0cbcee2)

![image](https://github.com/user-attachments/assets/5dfda67e-696f-4d86-a5ef-ee7b4fd8027f)

Con estos comandos:

· Se crean dos contenedores llamados contenedor8 y contenedor9.

· Ambos contenedores están conectados a la red mi_red_lan y tienen asignadas direcciones IP dentro del segmento local.

· Se usan como imagen la que hemos creado (mi_apache_web), y Apache se ejecuta automáticamente en ambos.

**Paso 7**

**Verificar contenedores**

verificar que los contenedores están corriendo con el siguiente comando:

docker ps

Muestra la lista de contenedores en ejecución, los dos que acabas de crear (contenedor8 y contenedor9).
![image](https://github.com/user-attachments/assets/af3ff17f-7d7a-4b9d-a787-c94e41664d9e)

**Paso 8**

**PROBAR LOS PUERTOS Y MOSTRAR IMAGEN**

Probar los puertos de los contenedores, para ver el mensaje del servidor Apache en cada contenedor.

![image](https://github.com/user-attachments/assets/939a9161-9b20-40ce-992b-f3f5669222ab)
Primera imagen del puerto 8088
![image](https://github.com/user-attachments/assets/393bbfb7-31e5-4efa-b33e-f824263d6dfe)
Segunda imagen en puerto 8089 modificado el mensaje y actualizado.
![image](https://github.com/user-attachments/assets/a95f61f7-83fa-4499-8bce-8c57c3eb9b0b)










