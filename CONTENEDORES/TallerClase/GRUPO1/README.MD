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
Crear un contenedor con un servidor web apache, que haga uso de una carpeta en local para guardar su desarollo web.</h3>



1.1	 se creo el archivo .html y el docker-compose.yml en la carpeta c: del equipo local
![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/Imagenes.jpg)


</ul>

<ul>
1.2	iniciamos el docker compose en power Shell, eso se hace para que se descargue la imagen de apache y crea e inicia el contenedor en segundo plano.

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/Imagen%202.jpg)

</ul>

<ul>
1.3	 verificamos que nuestro sitio web este corriendo

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/Imagen%203.jpg)

</ul>

<h4>Punto 2:	Debe tener asignada una IP válida en el segmento de conexión local lan.</h4>
<ul>
2.1 crear una red personalizada en docker

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%204.jpg)

</ul>
<ul>
2.2  verificamos que la red se creo correctamente

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%205.jpg)
</ul>
<ul>
2.3 conectar esta red con nuestro contenedor

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%206.jpg)
</ul>
<h5>Punto 3:	Se debe subir la imágen a dockerhub.</h5>
<ul>
3.1 crear el archivo dockerfile localmente

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%207.jpg)
</ul>

3.2 construir la imagen

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%208.jpg)

3.3 subir la imagen

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/imagen%209.jpg)

3.4 verificar en dockerhub

![image](https://github.com/jaiderospina/DevSecOps/blob/main/CONTENEDORES/TallerClase/GRUPO1/Imagen%2010.jpg)

4 Realizar un cambio en el html y actualizar el contenedor

4.1 se realiza el cambio en el archivo html

![image]CONTENEDORES/TallerClase/GRUPO1/imagen 11.png

</body>
</html>


