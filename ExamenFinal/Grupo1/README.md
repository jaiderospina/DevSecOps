
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

<ul>
<h3>
valuación y Priorización de Vulnerabilidades en un Entorno DevSecOps mediante CVSS 4.0  
</ul>

<ul>
<h3>
1-Elementos:
Se debe implementar un entorno de desarrollo ágil. Este incluye:
Un repositorio de código con una aplicación web básica.

Usamos WSL para entrar al entorno creado previamente de UBUNTU 
</ul>


![image](https://github.com/user-attachments/assets/7621a18f-51fc-4df0-8377-2288590428d1)



<ul>
<h3>
Se crea el entorno de desarrollo laravel con el comando “curl -s https://laravel.build/example-app | bashvv”

</ul>


![image](https://github.com/user-attachments/assets/e1415679-38ef-435e-beeb-a45457690e7f)

<ul>
<h3>
Creando recursos de red con comando “./vendor/bin/sail up”

</ul>


![image](https://github.com/user-attachments/assets/7aea075d-8e3a-4113-b9cd-f273e308912c)



<ul>
<h3>
Creación de imagen con laravel instalado

</ul>


![image](https://github.com/user-attachments/assets/d8e391c9-fc38-4173-9971-98a1dba1cd2e)


<ul>
<h3>
Instalación del contenedor de la base de datos

</ul>



![image](https://github.com/user-attachments/assets/b3849141-d1cf-4607-a1b3-254e18025de6)



![image](https://github.com/user-attachments/assets/f6bccad7-c818-4b34-a017-6710dcd1576e)


![image](https://github.com/user-attachments/assets/4a237013-545c-4271-8c9d-fba3e1da6ce8)



![image](https://github.com/user-attachments/assets/464648f8-5283-4b70-926c-19f9be9c1717)


![image](https://github.com/user-attachments/assets/22c5310e-8ba9-4090-82b5-39270120e9b9)



![image](https://github.com/user-attachments/assets/3fa59088-c36d-4cc4-88e0-c9f01fa6eba1)





<ul>
<h3>
Commit a GITHUB
</ul>




![image](https://github.com/user-attachments/assets/8ee45c5d-b995-4fcb-ae54-507e65ca4e5b)





![image](https://github.com/user-attachments/assets/55809d9a-7c8b-424b-a290-1bc20f2ba085)



<ul>
<h3>
Creación de repositorio en GITHUB
</ul>




![image](https://github.com/user-attachments/assets/6a097d7f-b57d-45ef-acba-409fb4c9771d)



<ul>
<h3>
Conexión de repositorio local con el remoto:
</ul>



![image](https://github.com/user-attachments/assets/8348f9af-5d94-40fc-b40b-b13fcd349c47)



<ul>
<h3>
Subir los archivos al repositorio remoto:
</ul>



![image](https://github.com/user-attachments/assets/a4a9c528-8a5a-4091-adb7-1c9f02df9499)





<ul>
<h3>
Se genera error al hacer el push y se genera token para poder hacer la sincronización y se logra de forma exitosa subir los archivos al repo.
</ul>




![image](https://github.com/user-attachments/assets/11d537a1-099e-4b0d-b7ee-4cbeb9c8e732)



<ul>
<h3>
Se confirma que los documentos del proyecto se subieron al repo de forma correcta.
•	Un sistema de CI/CD.
Inicialmente se crean 2 branch con el fin de identificar los cambios que se hagan en la rama DEV y posteriormente pasarlos a la rama main si se considera que el código es seguro para ejecutarlo.
</ul>




![image](https://github.com/user-attachments/assets/32858e1a-bbbb-45f5-a09f-2299e8ba67a9)


<ul>
<h3>

Posteriormente, se realiza la creación del workflow

</ul>




![image](https://github.com/user-attachments/assets/ba13a46f-6392-4540-afb8-543eb5480f81)



![image](https://github.com/user-attachments/assets/c6e4d7ef-d8c5-46e0-8c82-f6fbe22a9336)





<ul>
<h3>

Edición de flujo de trabajo en Visual Studio

</ul>




![image](https://github.com/user-attachments/assets/675d8801-4e43-4c36-b632-955653509fad)




<ul>
<h3>

TODO LO ANTERIOR FUE EJECUTADO DE FORMA LOCAL
Ahora hacemos git para agregar al repositorio de Github

</ul>




![image](https://github.com/user-attachments/assets/024278a1-df98-4aaa-8c56-30fe58dc404d)



<ul>
<h3>

Luego hacemos un git commit para comentar el cambio ejecutado

</ul>




![image](https://github.com/user-attachments/assets/cc91adcc-d738-4bfa-825e-6754350cdb60)



<ul>
<h3>

Luego hacemos push para que se actualice la información en el repositorio de GitHub

</ul>



![image](https://github.com/user-attachments/assets/d4be3cfb-55c6-44af-a676-2836d84ca2fc)





<ul>
<h3>
Se genera error y se actualiza el token para que permita ejecutar cambios en los workflows

</ul>




![image](https://github.com/user-attachments/assets/1e35d4b9-7544-4abd-8f82-54405f1fbbb8)




<ul>
<h3>
Push Exitoso.

Se identifica CI/CD en Github Actions y se genera error luego de instalar de forma correcta las dependencias.

</ul>





![image](https://github.com/user-attachments/assets/60d59f75-6563-430c-844f-afe412eb9b80)





<ul>
<h3>
Push Exitoso.
Se identifica que el archivo .env esta correctamente configurado y en la raíz del proyecto como debe ser. Se verifica que composer también se encuentra configurado correctamente.

file_get_contents(/home/runner/work/proyectofinaluniminuto/proyectofinaluniminuto/example-app/.env): Failed to open stream: No such file or directory

•	Un conjunto de vulnerabilidades simuladas (por ejemplo, en dependencias de software, configuraciones de infraestructura como código, y código fuente).

</ul>


<ul>
<h3>

Creación de archive dependabot.yml
Dependabot es una herramienta de GitHub que ayuda a mantener las dependencias de mi proyecto actualizadas automáticamente. Las dependencias son bibliotecas externas, frameworks o herramientas que tu proyecto utiliza para funcionar (por ejemplo, las mencionadas en el archivo composer.json para proyectos PHP).
El archivo .github/dependabot.yml es la configuración que le indica a Dependabot qué dependencias debe revisar, en qué directorios buscarlas y con qué frecuencia hacerlo.
Detección de vulnerabilidades: Si alguna de las dependencias tiene vulnerabilidades conocidas, Dependabot las identifica y puede sugerir actualizaciones a versiones más seguras.

</ul>




![image](https://github.com/user-attachments/assets/8a9618e5-7c07-4d97-8290-c0bb83f855ce)





<ul>
<h3>
Commit y Push

</ul>




![image](https://github.com/user-attachments/assets/382f338e-6f92-43a9-ac8b-7735df1e92cd)




<ul>
<h3>
El resultado de actualización se completa de forma exitosa como se observa a continuación.

</ul>




![image](https://github.com/user-attachments/assets/acd4c27e-1b99-4f9a-b820-1cac915508c6)




<ul>
<h3>
En la imagen anterior se identifica que actualmente las dependencias no contienen vulnerabilidades.
Se añaden al código vulnerabilidades para comprobar la efectividad si Github con su herramienta las detecta.

</ul>




![image](https://github.com/user-attachments/assets/ef2bdc68-fee1-4777-a103-62284447b73a)




<ul>
<h3>
Se realiza un escaneo con la herramienta integrada de GitHub y como se esperaba, se detectan vulnerabilidades en el código.

</ul>



![image](https://github.com/user-attachments/assets/24d4b0bb-a8bf-4014-af91-344e8cf6c5fe)




<ul>
<h3>
Tareas:
•	Identificación de Vulnerabilidades:
o	Ejecutar herramientas de análisis de seguridad como SAST, DAST, y escáneres de dependencias (por ejemplo, OWASP ZAP, Trivy, o SonarQube).
Al identificar vulnerabilidades en el código anteriormente, se procede a utilizar la herramienta Snyk, la cual nos permitirá evaluar las vulnerabilidades y posteriormente corregirlas.

</ul>




![image](https://github.com/user-attachments/assets/e3d697df-edcf-4fbb-86fe-46ec56621147)



<ul>
<h3>
Se integra Snyk con VS
</ul>




![image](https://github.com/user-attachments/assets/07a9599f-bc1b-49d0-9247-02787ca0640b)






<ul>
<h3>
Resultado del escaneo de vulnerabilidades con Snyk en VS con el código inicial.
</ul>



![image](https://github.com/user-attachments/assets/54faca8c-2e15-416d-985a-d02eb295dcee)




<ul>
<h3>
Resultado del escaneo de vulnerabilidades con Snyk en VS con el código con vulnerabilidades.
</ul>



![image](https://github.com/user-attachments/assets/822129b6-b0d3-49b8-956d-9abbd994c648)



<ul>
<h3>
Se verifica en Snyk y se identifica el total de vulnerabilidades encontradas en el código.
</ul>




![image](https://github.com/user-attachments/assets/daa63ac7-026d-4e04-9092-9a97cd6b77d3)






<ul>
<h3>
DOCUMENTACIÓN DE LAS VULNERABILIDADES ENCONTRADAS
</ul>





![image](https://github.com/user-attachments/assets/dcf368eb-16d8-4fb5-a597-8f77315c59c0)






<ul>
<h3>
Tipo de vulnerabilidad: Cross-site Scripting (XSS)
Nombre: Vulnerabilidad: CWE-79 - Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')
Descripción:
La vulnerabilidad CWE-79 es conocida como Cross-site Scripting (XSS). Ocurre cuando una aplicación web no neutraliza correctamente los datos proporcionados por el usuario antes de ser utilizados en la generación de contenido de una página web. Esta vulnerabilidad permite que un atacante inyecte código malicioso (generalmente JavaScript) en una página web, que luego se ejecuta en el navegador de otros usuarios que acceden a esa página.
</ul>


<ul>
<h3>
Vector de Ataque:
El vector de ataque en XSS es típicamente a través de entradas de usuario no validadas o mal validadas, que se reflejan, almacenan o manipulan en el DOM de la página sin ninguna sanitización adecuada. Los ataques XSS pueden ser reflejados, almacenados o basados en DOM.
•	Reflejado (Reflected XSS): El atacante envía un enlace malicioso con datos que contienen el código malicioso en parámetros de la URL o formularios, que luego es reflejado y ejecutado en el navegador del usuario.
•	Almacenado (Stored XSS): El código malicioso se almacena en la base de datos o en el servidor y luego se ejecuta cuando otro usuario carga la página con ese contenido malicioso.
•	Basado en DOM (DOM-based XSS): El código malicioso se ejecuta a través de manipulación insegura del DOM en el lado del cliente (navegador).
</ul>



<ul>
<h3>
Alcance:
•	Afecta: La vulnerabilidad afecta a las aplicaciones web que permiten la entrada de datos no validados por parte del usuario (por ejemplo, en formularios de comentarios, búsqueda o perfiles de usuario).
•	Riesgo: Un atacante puede robar información sensible, como cookies o credenciales de sesión, o redirigir a los usuarios a sitios maliciosos. También es posible ejecutar acciones no autorizadas en nombre del usuario víctima.
</ul>





![image](https://github.com/user-attachments/assets/1d9ff9a3-9c10-4bf5-8e41-5c2f283f1a87)








<ul>
<h3>
Tipo de vulnerabilidad: Command Injection
Nombre: CWE-78: Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection')
Descripción:
La vulnerabilidad CWE-78 se refiere a la inyección de comandos del sistema operativo (OS Command Injection). Esta vulnerabilidad ocurre cuando una aplicación web permite a un atacante insertar y ejecutar comandos del sistema operativo en el entorno de la máquina del servidor. Esto sucede cuando la entrada proporcionada por el usuario no es correctamente validada o sanitizada, permitiendo que comandos maliciosos sean ejecutados por el sistema operativo con los privilegios del proceso que ejecuta la aplicación.
</ul>


<ul>
<h3>
Vector de Ataque:
El vector de ataque de la inyección de comandos del sistema operativo generalmente involucra el envío de datos maliciosos a través de formularios, URL o parámetros de entrada de la aplicación web. Estos datos maliciosos se incorporan a un comando del sistema operativo ejecutado por la aplicación, lo que da como resultado la ejecución de comandos no autorizados en el sistema.
</ul>



<ul>
<h3>
Alcance:
•	Afecta: La vulnerabilidad afecta a aplicaciones que ejecutan comandos del sistema operativo sin validar correctamente la entrada del usuario, lo que incluye la mayoría de las aplicaciones que utilizan funciones como system(), exec(), shell_exec(), o popen() en PHP, Python, y otros lenguajes.
•	Riesgo: Un atacante podría comprometer la máquina del servidor, robar información confidencial, eliminar archivos, o ejecutar cualquier comando que esté disponible para la aplicación, afectando así la integridad, disponibilidad y confidencialidad del sistema.
</ul






![image](https://github.com/user-attachments/assets/c30ad1ae-9b76-4fba-9a77-cb48c53bfbcb)


























































