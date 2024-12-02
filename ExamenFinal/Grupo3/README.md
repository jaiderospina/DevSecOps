## EXAMEN FINAL

## Integrantes Grupo


> - Ingrid Paola Quiroga
> - Juan Alvarez
> - Brayan Hernandez
> - Monica Florez Mejia
> - Alejandro Cortes
> - Charles Guerrero

---
<h2 style="text-align:center">Desarrollo del Examen Final</h2>

En las siguientes imagenes y informacion se explicará detalladamente de escaneo de una vulnerabilidad, mediante una aplicacion llamada

<br></br>

----

<h2 style="text-align:center">Introduccion</h2>

La gestión de vulnerabilidades es una parte crítica de cualquier estrategia de seguridad cibernética. En entornos DevSecOps, donde el desarrollo y la seguridad se integran de manera continua, la identificación y priorización de vulnerabilidades deben realizarse de manera ágil y efectiva. En este contexto, el uso del Sistema Común de Puntuación de Vulnerabilidades (CVSS, por sus siglas en inglés) se presenta como una herramienta valiosa para clasificar y priorizar las vulnerabilidades, permitiendo a los equipos de desarrollo y operaciones tomar decisiones informadas sobre qué problemas deben abordarse con urgencia.

Este informe aborda cómo se puede aplicar CVSS en un entorno DevSecOps para la priorización de vulnerabilidades, considerando los desafíos, las mejores prácticas y los beneficios de este enfoque.

<br></br>

--
<br></br>

### Paso 1 :white_check_mark:

> - se crea el repositorio de la aplicación 

![image](https://github.com/user-attachments/assets/4638c2b7-d278-4a5b-9ec9-84bed411786f)

---

<br></br>



2-código de la aplicación 

![image](https://github.com/user-attachments/assets/26e881e8-44ea-4696-a30e-9c07e4575c12)


---

<br></br>



3-Aplicación corriendo en local 

![image](https://github.com/user-attachments/assets/8aceca9d-65b2-40e3-8702-f0629cdbca1a)


---

<br></br>



4-entramos a la consola de snyk  

![image](https://github.com/user-attachments/assets/c9488861-b77c-40d9-a4ae-a0d50b31777b)
![image](https://github.com/user-attachments/assets/b8560979-388d-49be-a334-11fda41bcd7e)

---

<br></br>



5-Vulnerabilidades.

![image](https://github.com/user-attachments/assets/649defee-091a-4c7b-8d88-7abd56225562)


![image](https://github.com/user-attachments/assets/31dc8d8d-919c-4fc2-b5e2-8165ce3b1a55)


---

<br></br>


6-https://cwe.mitre.org/data/definitions/78.html 
![image](https://github.com/user-attachments/assets/c2c7bd9f-b356-4147-b76c-12b9e61ea8e1)


---

<br></br>


7.Lista priorizada.

![image](https://github.com/user-attachments/assets/602b1153-3745-42b2-8de2-d3552e40b643)


---

<br></br>


8.Instalamos nmap desde py para la evaluacion cvss3 
![image](https://github.com/user-attachments/assets/5862b5ae-1105-46eb-be46-d8b44287249a)


---

<br></br>


9.Creamos el archivo de configuración para el escaneo 

![image](https://github.com/user-attachments/assets/5ea2a14a-87ba-49c6-8fa2-5b4b517d135b)

---

<br></br>


10.Creamos el docker para correr

![image](https://github.com/user-attachments/assets/026bc50b-80b4-4a2e-b8b7-b5f7c259473f)



---

<br></br>





11. Construimos la imagen.

    
![image](https://github.com/user-attachments/assets/7f7b8f4e-b45c-4136-8182-d68979d071d2)


---

<br></br>


12.Ejecutamos el contenedor


![image](https://github.com/user-attachments/assets/fc34b0de-f13b-4b5e-9256-a1a5c685d58e)


---

<br></br>


13.Configuramos la ruta del contenedor a escanear
![image](https://github.com/user-attachments/assets/b36ebc5f-bfb0-4dba-ab8a-6f47dd7cdd04)


https://github.com/acortes2/examen_devsecops













