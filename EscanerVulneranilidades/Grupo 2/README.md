Adriana Tobón Dávila.


                          Taller Escaneo de Vulnerabilidades.
PUNTO 1
Crear un contenedor de Openvas.

1.	Se realiza la instalacion de paquetes Debian/Ubuntu.
 ![image](https://github.com/user-attachments/assets/788d6641-4125-4b78-9f46-74908b531f05)

INSTALACIÓN DE DOCKER 
2.	Se debe instalar Docker para ejecutar los servicios dentro de los contenedores. 
 ![image](https://github.com/user-attachments/assets/4eabc341-3583-453b-bc0b-68814169c3c1)

	CONFIGURACIÓN 
3.	Ahora se configura el repositorio de Docker.
 ![image](https://github.com/user-attachments/assets/4f6ad4d0-5b33-4fa0-a8c3-bffd1c2b1176)

4.	Instalar paquetes Docker Debian.
 
![image](https://github.com/user-attachments/assets/847322ce-7f25-4b30-b577-5aaa25023300)



5.	Se debe dar permiso de super user para permitir que el usuario ejecutre Docker. 
 ![image](https://github.com/user-attachments/assets/45d1b21f-e783-4365-8667-b460f7724e0e)


ARCHIVO DOCKER COMPOSE 
6.	Para descargar el archivo docker compose de Greenbone Community Edition, se debe crear un directorio de destino.
 
![image](https://github.com/user-attachments/assets/dfe566b5-8722-4fba-bc6b-84c6d17fb878)

![image](https://github.com/user-attachments/assets/c12662ee-84d0-4fb2-b1dc-b6d67e7c7dc9)


6.1	Para ejecutar Greenbone Community Edition con contenedores, se debe utilizar el siguiente archivo de composición:
 ![image](https://github.com/user-attachments/assets/1b01edee-7bda-40e4-838c-f9fab560b1d7)


INICIANDO LOS CONTENEDORES COMUNITARIOS DE GREENBONE 
7.	Usando el archivo docker compose, se pueden descargar ( extraer ) las imágenes del contenedor y se pueden iniciar los contenedores en segundo plano.
 
 ![image](https://github.com/user-attachments/assets/db3e1e15-3505-4ebb-81b4-1fb713526c2e)
![image](https://github.com/user-attachments/assets/33ebf1b5-9dcb-4947-b1ca-e99b0f9b5930)


7.1 Puesta en marcha de los contenedores comunitarios Greenbone.
 ![image](https://github.com/user-attachments/assets/e144902d-3480-48eb-9eae-6f7b89f03be6)


8.	Mostrar mensajes de registro de todos los servicios de los contenedores en ejecución.
 
 ![image](https://github.com/user-attachments/assets/54091513-e497-4b4b-ac02-daa01d1dbaad)
![image](https://github.com/user-attachments/assets/f81c3b8f-c43e-4f92-9923-b0a9e9a3dbf3)


INICIANDO LA GESTIÓN DE VULNERABILIDADES 
9.	El navegador mostrará la página de inicio de sesión de GSA y, después de usar las credenciales creadas anteriormente, es posible comenzar con el escaneo de vulnerabilidades.
![image](https://github.com/user-attachments/assets/ee4d6dda-ca83-49e2-9af9-5f9307c58b20)
![image](https://github.com/user-attachments/assets/1ec6a25b-5ca3-41ca-b63f-a7db9b5c9fa4)

 
 
CONFIGURACIÓN Y SECUENCIA DE COMANDOS DE INICIO 
10.	Descargar el script de instalación e inicio al directorio de trabajo actual
 ![image](https://github.com/user-attachments/assets/f7616f02-22ba-49ae-8341-428f7d5622c6)

10.1 Para ejecutar el script se debe ejecutar el siguiente comando
 ![image](https://github.com/user-attachments/assets/f020ce1d-82f8-4686-9f35-4e405b331e89)


11.	Actualizar el contenedor creado con la base de datos de vulnerabilidades, docker exec -it bash
 ![image](https://github.com/user-attachments/assets/8fd84bbb-149e-4b77-af15-1e623439e8e2)

PUNTO 2.
1. Actualizar el contenedor creado con el motor de base de datos de vulnerabilidades.
![image](https://github.com/user-attachments/assets/789b741f-e591-4417-80dc-208a00f1208a)
![image](https://github.com/user-attachments/assets/a1c527cd-e6ca-4dd2-a180-7749daa721f4)

PUNTO 3.
Descargar un contenedor vulnerable desde dockerhub y realizar un escaneo de vulnerabilidades al mismo.
![image](https://github.com/user-attachments/assets/5a0faee1-2546-4f07-9d11-282ca4d2bb26)

3.1 Iniciamos el contenedor vulnerable.
![image](https://github.com/user-attachments/assets/3c7a324f-64a1-4bd1-af9f-22eab2538994)

3.2 Mostramos que la pagina de DVWA si esta funcionando.
![image](https://github.com/user-attachments/assets/a13024fd-7d96-4cb5-bda3-7184b084a39b)




