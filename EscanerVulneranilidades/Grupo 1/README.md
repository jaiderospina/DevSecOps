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


