<html>
<head>
<div align = "center">
<h1>Grupo 1</h1>
</div>
</head>
<body>
<h2>Integrantes:</h2>

<ul>
<li><strong>Fredys Marquez</strong></li>
<li><strong>Carlos Mayorga</strong></li>
<li><strong>Felipe Caicedo</strong></li>
<li><strong>Ricardo Clavijo</strong></li>
</ul>

<div align = "center">
Documentación del Taller Realizado
</div>

<ul>
<h3>Punto 1:
1.Instalar paquetes Debian/Ubuntu ca-certificates, curl y gnupg 
  
![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/1.png)

1.1 Instalar docker 
1.2	Desinstalar paquetes Debian conflictivos
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt remove $pkg; done

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/2.png)

</ul>

<ul>

1.3	Configurar el repositorio docker
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/3.png)

</ul>

<ul>
1.4	 Instalar paquetes Docker Debian
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin


![image]( https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/4.png)

</ul>

</ul>

<ul>
1.5.Configuración 
Para permitir que el usuario actual ejecute Docker y, por lo tanto, inicie los contenedores, se lo debe agregar al grupo de usuarios de Docker . Para que el cambio de grupo sea efectivo, cierre la sesión y vuelva a iniciarla o use su.
<ul>
3.1 Agregue el usuario actual al grupo de Docker y aplique los cambios del grupo para el entorno de shell actua


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/5.png)

<ul>

<ul>
1.6 Para descargar el archivo docker compose de Greenbone Community Edition, se debe crear un directorio de destino.
Crear directorio de descarga
export DOWNLOAD_DIR=$HOME/greenbone-community-container && mkdir -p $DOWNLOAD_DIR

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/6.png)

</ul>

<ul>
1.7.Archivo Docker Compose ¶
Para ejecutar Greenbone Community Edition con contenedores, se debe utilizar el siguiente archivo de composición:
  <ul>
1.8 se descarga la imagen directamente con el siguiente comando:
cd $DOWNLOAD_DIR && curl -f -L https://greenbone.github.io/docs/latest/_static/docker-compose-22.4.yml -o docker-compose.yml
</ul>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/7.png)


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/16.png)


</ul>
<ul>
1.9 Iniciando los contenedores comunitarios de Greenbone 
Usando el archivo docker compose, se pueden descargar ( extraer ) las imágenes del contenedor y se pueden iniciar los contenedores en segundo plano.
  </ul>
1.10 Para eso utilizamos el siguiente comando
Descarga de los contenedores comunitarios de Greenbone
docker compose -f $DOWNLOAD_DIR/docker-compose.yml -p greenbone-community-edition pull
  <ul>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/8.png)
</ul>
<ul>
1.11 Para obtener un flujo continuo de la salida del registro de todos los servicios, ejecute el siguiente comando:
Mostrar mensajes de registro de todos los servicios de los contenedores en ejecución
docker compose -f $DOWNLOAD_DIR/docker-compose.yml -p greenbone-community-edition logs –f

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/9.png)
</ul>

<ul>
1.12 Puesta en marcha de los contenedores comunitarios Greenbone

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/10.png)
</ul>
<ul>
1.13 Iniciando la Gestión de Vulnerabilidades 
Una vez iniciados los servicios y cargados todos los datos de las fuentes , se puede abrir la interfaz web de Greenbone Security Assistant (GSA) en el navegador.
Cómo abrir Greenbone Security Assistant en el navegador
xdg-open "http://127.0.0.1:9392" 2>/dev/null >/dev/null &

![image]( https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/11.png)
</ul>
<ul>
El navegador mostrará la página de inicio de sesión de GSA y, después de usar las credenciales creadas anteriormente, es posible comenzar con el escaneo de vulnerabilidades

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/12.png)
</ul>
<ul>
  
4.6 Configuración y secuencia de comandos de inicio
Descargar el script de instalación e inicio al directorio de trabajo actual
curl -f -O https://greenbone.github.io/docs/latest/_static/setup-and-start-greenbone-community-edition.sh && chmod u+x setup-and-start-greenbone-community-edition.sh

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/13.png)
</ul>
<ul>
4.7 Para ejecutar el script se debe ejecutar el siguiente comando
Ejecutar la configuración y comenzar el script

![image]( https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/14.png)
</ul>

<ul>
<h3>
Configuración y secuencia de comandos de inicio 
.</h3>

![image]( https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/17.png)

<ul>
<h3>
Recuerde seguir primero las instrucciones descritas en los Requisitos previos .
Como solución rápida, proporcionamos todos los comandos anteriores en un solo script. Este script se puede descargar directamente con el siguiente comando:
Descargar el script de instalación e inicio al directorio de trabajo actual.</h3>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/18.png)

<ul>
<h3>
Para ejecutar el script se debe ejecutar el siguiente comando
Ejecutar la configuración y comenzar el script
.</h3>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/19.png)

2.Dar al contenedor una IP valida dentro del segmento local

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2060.PNG)

3 Actualizar las bases de datos
Actualizar el contenedor creado con el motor de base de datos de vulnerabilidades.


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen30.png)

3.1 una vez descargado se debe dar permiso de ejecución al archivo

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen31.jpg)

3.2 se procede a ejecutar el script para instalar la actualización 

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2032.jpg)

3.3 se procede a realizar el escaneo de vulnerabilidades.

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/20.png)

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/21.png)

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/22.png)


</ul>



</ul>

<ul>
4. Realizar y documentar un escaneo a otro contenedor o máquina vulnerable.

</ul>
</ul>

<ul>
4.1 Descargar la imagen de DVWA desde Docker Hub:
docker pull vulnerables/web-dvwa


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/23.png)

</ul>

</ul>

<ul>
4.2 Iniciar el contenedor vulnerable:
docker run -d -p 80:80 --name dvwa vulnerables/web-dvwa


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/24.png)

</ul>

</ul>

<ul>
4.3 Acceder a la aplicación web vulnerable:
Abre tu navegador y navega a http://localhost para verificar que la aplicación DVWA esté funcionando. Deberías ver una página de inicio de sesión. Si es la primera vez que ejecutas el contenedor, puedes ingresar con las credenciales predeterminadas (usuario: admin, contraseña: password).


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/25.png)

</ul>

</ul>

<ul>
4.4 Ejemplo de ataque

Ataque de inyección sql manual
El ataque consite en inyectar sentencias SQL a través de los imputs del aplicativo web vulnerable, para la manipulación de bases de datos.


Paso 1
En la opción “SQL INYECTION” del aplicativo web ejecutamos el parámetro ´or ´1=1 en la casilla de user id 

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2035.PNG)

Se obtiene los datos first name y Surname

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2036.PNG)

Ejemplo 2 

Otro ejemplo de este tipo de ataque que se puede realizar es insertando el siguiente script
Seleccionar la opción “SQL Inyection” del aplicativo web, ejecutar el parámetro 1`or 1=1 union select null, table_name from information_schema.tables# en la entrada de texto “User ID” del aplicativo web.

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2037.PNG)


5 Se realiza la autenticación en docker 
![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/imagen%2033.jpg)

5.1 Se crea la imagen en docker 

![image](https://github.com/user-attachments/assets/4eedb19c-51ff-4dbf-848c-214e657d708f)

5.2 Se verifica que la imagen este cargada

![image](https://github.com/user-attachments/assets/f819139d-1f3d-4155-b1ca-878c7d9769d8)

5.3 Se sube la imagen a docker

![image](https://github.com/user-attachments/assets/6bb73638-80bb-483c-8908-668f438bd5d0)

5.4 Se verifica que la imagen quedo cargada

![image](https://github.com/user-attachments/assets/8ad15b23-3470-4ed8-8862-2258a160fa46)








</ul>


</body>
</html>

