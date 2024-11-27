## Integrantes Grupo

> - Monica Florez
> - Juan Alvarez
> - Brayan Hernandez

## *Taller en clase*

## Crear un contenedor con un servidor web apache, que haga uso de una carpeta en local para guardar su desarollo web.

---

<h2 style="text-align:center">Desarrollo del taller</h2>

En las siguientes imagenes se explicará detalladamente el proceso para crear un contenedor que ejecuta un servidor web Apache. Además, se mostrara la respectiva configurarácion de el contenedor para que se utilice en una carpeta local en el sistema como directorio de almacenamiento del desarrollo web, permitiendo así una interacción directa entre el entorno local y el servidor dentro del contenedor
<br></br>

### Paso 1 :white_check_mark:

> - Creamos la carpeta de forma local en el equipo, en este caso la creamos en kali linux y la nombramos como grupo5

#### Comando de la terminal

```bash
mkdir grupo5
```

![image](https://github.com/user-attachments/assets/efc86b16-ffd3-481a-949e-cba953e427a0 "imagen creando una carpeta")

---

<br></br>

### Paso 2 :white_check_mark:

> - Creamos dentro de la carpeta **'grupo5'** un archivo de docker que se nombra como dockerfile

#### Comando de la terminal

```bash
touch dockerfile
```

![image](https://github.com/user-attachments/assets/45142c82-09ef-49fd-9772-9e6ed6258e07 "Imagen de la creacion del archivo dockerfile")

#### Contenido del archivo dockerfile

```docker
FROM httpd:2.4

COPY ./html/ /usr/local/apache2/htdocs/

EXPOSE 80
```

---

<br></br>

<!--Estamos aqui-->

### Paso 3 :white_check_mark:

> - Creamos una nueva carpeta dentro de **'grupo5'** llamada html

#### Comando de la terminal

```bash
mkdir html
```
![image](https://github.com/user-attachments/assets/5a8482ac-c32a-4f04-961a-249b664ec908)

> - Dentro de la carpeta **'html'** creamos un archivo index.html el cual contiene estructura de la pagina

#### Comando de la terminal

```bash
touch index.html
```
![image](https://github.com/user-attachments/assets/5099302d-be16-44b6-a9b3-b455f9338546)

>* Dentro del archivo de **'index.html'** creamos la arquitectura de la pagina web

#### index.html

```html
<!DOCTYPE html>
<html lang="es">
<head><title>Grupo 5</title></head>
<body style="height: 98vh; display: flex; flex-direction: column; justify-content: center; align-items: center;" >
    <h1 style="font-size: 50px;" >Hola Mundo somos el GRUPO 5</h1>
</body>
</html>
```

---

<br></br>

### Paso 4 :white_check_mark:

> - Ya teniendo los pasos anteriores correctamente procedemos a crear la image de docker de nuestro servio web

#### Comando de la terminal

```bash
docker build -t grupo5 .
```

![image](https://github.com/user-attachments/assets/44f3c438-c5f9-49f9-9327-ddb224075366)

---

<br></br>

### Paso 5 :white_check_mark:

> * Despues de crear la imagen de nuestro servicio iniciamos el contenedor

#### Comando de la terminal

```bash
docker run --rm -d -p 80:80/tpc grupo5:latest
```

### Explicación de los comandos anteriores

**docker run:**

>* Este es el comando básico para ejecutar un contenedor en Docker. Lo que hace es crear un contenedor a partir de una imagen y ejecutarlo.

**--rm:**

>* Esta opción le indica a Docker que elimine el contenedor automáticamente cuando se detenga. Es útil para evitar acumular contenedores detenidos innecesarios en el sistema.

**-d (Modo independiente):**

>* Ejecuta el contenedor en "modo desapegado" (detached), es decir, en segundo plano. Si no usas esta opción, el contenedor se ejecutaría en primer plano y el terminal quedaría bloqueado.

**-p 80:80/tcp:**

>* Este parámetro mapea el puerto 80 del contenedor al puerto 80 del host, utilizando el protocolo TCP.
>* El primer 80 es el puerto del host (el sistema donde estás ejecutando Docker).
>* El segundo 80 es el puerto dentro del contenedor (la aplicación que está ejecutándose dentro del contenedor).
>* El tcp indica que estás exponiendo el puerto utilizando el protocolo TCP, que es el predeterminado, por lo que a veces podrías omitirlo, pero es explícito aquí.

**grupo5:latest:**

>* Este es el nombre de la imagen de Docker que se va a ejecutar. En este caso, es grupo5 y la etiqueta latest significa que se usará la última versión de esta imagen.

![image](https://github.com/user-attachments/assets/6dc73b94-5210-45c3-9bd7-1d1926f9e7d0)

___
<br></br>

### Paso 6 :white_check_mark:

> * Por ultimo ejecutamos lo siguiente en el navegador **http://localhost:80:80** y podremos visulizar el mensaje que colocamos

#### Url a ejecutar en el navegador para verificar el servicio web

```
http://localhost:80:80
```

![image](https://github.com/user-attachments/assets/110597b0-eb3f-4495-9a13-26fb41d34982)

___
<br></br>

### Paso 7 :white_check_mark:

> * Despues de que  iniciamos el contenedor podemos ver el estado del contenedor junto a varios atributos importates con el siguiente comando:

#### Comando para ver el estado del contenedor
```bash
docker ps
```

![image](https://github.com/user-attachments/assets/e90aece3-df0c-4f3d-b166-aa75cc5f94a1)

>* Uno de los atributos importantes es el **'CONTAINER ID'** es el identidicador del contenedor el cual nos puede ayudar a parar el contenedor

#### Comando de la terminal para parar el contenedor

```bash
docker stop eaabcaca0ec5a2
```

![img](https://github.com/user-attachments/assets/809f7a8b-52d0-49e2-8a3f-fd61b3944923)




### Paso 8 ASIGNACION DE IP :white_check_mark:

> * Despues procedemos a asignar una subred a nuestro contenedor con el siguiente comando

#### Comando para ver el estado del contenedor
```bash
docker network create --subnet=192.168.1.0/24   my_network
```

![image](https://github.com/user-attachments/assets/c00f7c8d-46dd-46f9-983c-3a325e0b009f)


> * Despues procedemos a asignar una ip a nuestro contenedor con el siguiente comando

#### Comando para ver el estado del contenedor
```bash
docker run -d --name my_container --net my_network --ip 192.168.1.100 my_image
```



Despues procedemos a ejecutar la ip  en el navegador

![image](https://github.com/user-attachments/assets/15f5153c-7f16-4b26-8c80-66dc4f1dffb2)






