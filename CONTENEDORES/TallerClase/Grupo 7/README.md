
# Taller en Clase

## Integrantes del Grupo 7

| Nombre      | Apellido     |
|-------------|--------------|
| Michelle    | Gutierrez    |
| Harold      | Ramirez      |
| Camilo      | Porras       |

---

## **Descripción del Proyecto**

El objetivo del taller fue implementar un servidor Apache utilizando Docker y configurar el acceso a una página web estática. Este proceso incluyó:

Creación de imágenes Docker personalizadas.
Configuración de una red local con asignación de IPs.
Pruebas de acceso desde el navegador.
Publicación de la imagen en Docker Hub.

## Descripción
```mermaid
graph TD;
    A-->Carpeta_httpd_apache;
    A-->B;
    B-->Creacion_index.html;
    B-->Asignacion_de_ip;
    B-->C;
    C-->test_localhost;
    C-->upload_imagen_docker;
```
**1.**	Creación de una carpeta local con el nombre /apache-cerver-grupo-7/html

 ![image](https://github.com/user-attachments/assets/8c035ca4-a76f-44cc-a637-32152d40f0f8)


**2.**	Creación de un archivo de nombre index.html, con el contenido de la pagina

 ![image](https://github.com/user-attachments/assets/6c3a3ee9-b678-4b07-8d69-0ab200aeef6e)
![image](https://github.com/user-attachments/assets/6361b680-46f4-4c51-a268-98ab4ac4d570)

 
**3.**	Creación del archivo Dockerfile
El Dockerfile se utilizó para construir la imagen personalizada de Apache:

FROM httpd:latest
COPY ./html /usr/local/apache2/htdocs/

 ![image](https://github.com/user-attachments/assets/7ac44f5d-f304-4d7d-a5bf-0637956d37f7)


**4.**	Construcción de la imagen apache-local con la etiqueta 1.0 haciendo relación a que es la primera versión del archivo

![image](https://github.com/user-attachments/assets/bcddb604-d659-46f7-a175-7ca56e2c5d98)

 
**5.**	Asignación de una IP del segmento 10.0.2.0/24, en este caso la 10.0.2.30

![image](https://github.com/user-attachments/assets/63618ba2-ddaf-4082-94dd-cee99df86966)

 
**6.**	Se accede a la ip en el navegador para confirmar el acceso a la pagina creada

 ![image](https://github.com/user-attachments/assets/f3dec105-8e3b-4d40-8450-151dd9bf4386)


**7.**	Se procede a conectarse a Docker Hub para subir la imagen

 ![image](https://github.com/user-attachments/assets/e1bec824-5b27-4d75-b423-fd6ccae3de17)
![image](https://github.com/user-attachments/assets/e6e99dce-b354-4466-b6ee-a476ab023191)

MIT License

Copyright (c) 2024 Grupo 7

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
...

