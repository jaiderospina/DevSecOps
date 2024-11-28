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




2.	Instalar docker 
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

<h4>3.Configuración ¶
Para permitir que el usuario actual ejecute Docker y, por lo tanto, inicie los contenedores, se lo debe agregar al grupo de usuarios de Docker . Para que el cambio de grupo sea efectivo, cierre la sesión y vuelva a iniciarla o use su.
</h4>
3.1 Agregue el usuario actual al grupo de Docker y aplique los cambios del grupo para el entorno de shell actua


![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/5.png)



<ul>

<ul>
3.2 Para descargar el archivo docker compose de Greenbone Community Edition, se debe crear un directorio de destino.
Crear directorio de descarga
export DOWNLOAD_DIR=$HOME/greenbone-community-container && mkdir -p $DOWNLOAD_DIR

![image](https://github.com/jaiderospina/DevSecOps/blob/main/EscanerVulneranilidades/Grupo%201/6.png)

</ul>


