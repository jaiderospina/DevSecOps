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

2 Instalar docker 
2.1	Desinstalar paquetes Debian conflictivos
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt remove $pkg; done

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/2.png)

</ul>

<ul>

2.1	Configurar el repositorio docker
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
2.3	 Instalar paquetes Docker Debian
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin


![image]( https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/4.png)

</ul>

</ul>

<ul>
3.Configuración 
Para permitir que el usuario actual ejecute Docker y, por lo tanto, inicie los contenedores, se lo debe agregar al grupo de usuarios de Docker . Para que el cambio de grupo sea efectivo, cierre la sesión y vuelva a iniciarla o use su.
<ul>
3.1 Agregue el usuario actual al grupo de Docker y aplique los cambios del grupo para el entorno de shell actua


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/5.png)

<ul>

<ul>
3.2 Para descargar el archivo docker compose de Greenbone Community Edition, se debe crear un directorio de destino.
Crear directorio de descarga
export DOWNLOAD_DIR=$HOME/greenbone-community-container && mkdir -p $DOWNLOAD_DIR

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/6.png)

</ul>

<ul>
4.Archivo Docker Compose ¶
Para ejecutar Greenbone Community Edition con contenedores, se debe utilizar el siguiente archivo de composición:
  <ul>
4.1 se descarga la imagen directamente con el siguiente comando:
cd $DOWNLOAD_DIR && curl -f -L https://greenbone.github.io/docs/latest/_static/docker-compose-22.4.yml -o docker-compose.yml
</ul>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/7.png)


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/16.png)


</ul>
<ul>
4.2 Iniciando los contenedores comunitarios de Greenbone 
Usando el archivo docker compose, se pueden descargar ( extraer ) las imágenes del contenedor y se pueden iniciar los contenedores en segundo plano.
  </ul>
4.3 Para eso utilizamos el siguiente comando
Descarga de los contenedores comunitarios de Greenbone
docker compose -f $DOWNLOAD_DIR/docker-compose.yml -p greenbone-community-edition pull
  <ul>

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/8.png)
</ul>
<ul>
4.4 Para obtener un flujo continuo de la salida del registro de todos los servicios, ejecute el siguiente comando:
Mostrar mensajes de registro de todos los servicios de los contenedores en ejecución
docker compose -f $DOWNLOAD_DIR/docker-compose.yml -p greenbone-community-edition logs –f

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/9.png)
</ul>

<ul>
4.4 Puesta en marcha de los contenedores comunitarios Greenbone

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/10.png)
</ul>
<ul>
4.5 Iniciando la Gestión de Vulnerabilidades 
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
2 punto del taller 
Actualizar el contenedor creado con el motor de base de datos de vulnerabilidades.
docker exec -it <nombre_del_contenedor> bash

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/15.png)

</ul>

</body>
</html>

