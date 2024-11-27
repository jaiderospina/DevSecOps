### **Grupo 8**
**Interante**
- Diego Alejandro Padilla Huepo.

---
**Taller de contenerizacion**
- El siguiente trabajo vamos a crear dos contenedores con el servicio de apache y a cada uno se le asignara una IP, ambos contenedores van a consultar el mismo archivo HTML, cuando se modifique dicho archivo se debe que ver reflejado en los dos contenedores.
---
**Requisitos:**
-	Docker
-	Conexión a la red local LAN
-	Carpeta local para los archivos web

**1. Crear las carpetas locales para el desarrollo web:** 
Creamos una carpeta en el sistema que se usara para almacenar el archivo html de consulta de los apaches:
En la terminal Ingresamos a la carpeta local donde vamos a tener nuestro archivo HTML para abrirlo con los dos contenedores apache
EL comando para ingresar a la carpeta es:

```bash
Cd /home/cosmo/Documentos
```

Estando hay creamos la carpeta donde almacenaremos nuestro archivbo HTML

```bash
mkdir -p /home/cosmo/Documentos/Apache
```

**Explicación del comando:**
- **cd:** es el comando para cambiar de  directorio 
- **mkdir:** Es el comando utilizado para crear directorios.
- **-p:** Es una opción (flag) que se pasa al comando mkdir para agregar una funcionalidad especial y crear varias carpetas al tiempo en la misma ruta y no una por una.
  
![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/1.jpg)

**2. Crear el archivo HTML:**
creamos un archivo HTML utilizando el comando touch o directamente editándolo con un editor de texto.
Primero, crea el archivo HTML: para este caso nuestro archivo se llamara Docapa.html

```bash
touch Docapa.html
```

Este comando creará un archivo vacío llamado docapa.html en el directorio actual.
**Usando un editor de texto:**
Ahora, abrimos el archivo con un editor de texto, por ejemplo, nano:

```bash
nano archivo.html
```

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/2.jpg)

**3. Escribir el contenido del archivo HTML:**
Dentro del editor (como nano), escribimos el siguiente código HTML básico:

```bash
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grupo 8 Ejercicio </title>
</head>
<body>
    <h1>Bienvenidos al ejercicio de Docker y apache - Grupo 8</h1>
    <p>este es un ejercicio de contenerizacion.</p>
</body>
</html>
```

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/3.jpg)

**4. Guardar el archivo:**
En nano, para guardar el archivo, presiona Ctrl + O, luego presiona Enter para confirmar. Para salir de nano, presiona Ctrl + X.
**5. Configurar la red en Docker:**
Para asignar IPs específicas a los contenedores dentro de tu red LAN, primero necesitamos crear una red personalizada en Docker.
Ejecuta el siguiente comando para crear una red bridge personalizada:

```bash
docker network create --subnet=192.168.1.0/24 mi_red
```

Esto crea una red en el segmento de la LAN (192.168.1.0/24) que puedes usar para asignar direcciones IP estáticas a los contenedores.

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/4.jpg)

**6. Crear y ejecutar los contenedores:**
Ahora vamos a crear dos contenedores Docker con Apache, asignando las carpetas locales como volúmenes y configurando las IPs estáticas para cada uno.
** - Contenedor 1:**
Ejecuta el siguiente comando para crear el primer contenedor:

```bash
docker run -d \ 
--name contenedor1 \ 
--network mi_red \ 
--ip 192.168.1.10 \ 
-v /home/cosmo/Documentos/Apache:/usr/local/apache2/htdocs \ 
httpd:2.4
```

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/5.jpg)

** - Contenedor 2:**
Ejecuta el siguiente comando para crear el segundo contenedor:
```bash
docker run -d \ 
--name contenedor2 \ 
--network mi_red \ 
--ip 192.168.1.11\ 
-v /home/cosmo/Documentos/Apache:/usr/local/apache2/htdocs \ 
httpd:2.4
```

**Explicación del comando:**
-	-d: Ejecuta el contenedor en segundo plano.
-	--name (contenedor1) o (contenedor2) según el contenedor que deseamos crear.
-	--network mi_red_lan: Asocia el contenedor a la red mi_red.
-	--ip (192.168.1.10) o (192.168.1.11): Asigna la IP estática al contenedor.
-	v /home/cosmo/Documentos/Apache:/usr/local/apache2/htdocs \ Asocia la carpeta local apache con el directorio usr/local/apache2/htdocs en el contenedor (directorio raíz de Apache).
-	httpd: Es la imagen oficial de Apache.

**7. Verificar el funcionamiento de los contenedores:**
Después de ejecutar los contenedores, puedes verificar que los servidores Apache están corriendo en las direcciones IP asignadas. Abre un navegador y prueba acceder a las IPs de los contenedores:
- http://192.168.1.10 para el contenedor 1

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/6.jpg)

- •	http://192.168.1.11 para el contenedor 2

![Primer paso](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/Grupo%208/7.jpg)  

---
**Comandos para recordar**
- docker --version: Validar la version de docker y si esta instalado.
- docker ps -a: Validar el listado de todos los contenedores incluyendo hasta los que estan detenidos
- docker start **(nombre del contenedor)**: Iniciamos el contenedor selecionado previamente 
