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

En el siguiente informe se presentarán las imágenes y la información detallada sobre el escaneo de una vulnerabilidad, utilizando una aplicación llamada..

<br></br>

----

<h2 style="text-align:center">Introduccion</h2>

La gestión de vulnerabilidades es una parte crítica de cualquier estrategia de seguridad cibernética. En entornos DevSecOps, donde el desarrollo y la seguridad se integran de manera continua, la identificación y priorización de vulnerabilidades deben realizarse de manera ágil y efectiva. En este contexto, el uso del Sistema Común de Puntuación de Vulnerabilidades (CVSS, por sus siglas en inglés) se presenta como una herramienta valiosa para clasificar y priorizar las vulnerabilidades, permitiendo a los equipos de desarrollo y operaciones tomar decisiones informadas sobre qué problemas deben abordarse con urgencia.

Este informe aborda cómo se puede aplicar CVSS en un entorno DevSecOps para la priorización de vulnerabilidades, considerando los desafíos, las mejores prácticas y los beneficios de este enfoque.


<h2 style="text-align:center">Qué es el CVSS</h2>

El Common Vulnerability Scoring System (CVSS) es un marco abierto y estándar utilizado para evaluar la gravedad de las vulnerabilidades de seguridad en software y sistemas. CVSS proporciona una puntuación numérica en una escala de 0 a 10, que refleja la gravedad de una vulnerabilidad, permitiendo priorizar las acciones correctivas en función de su impacto y facilidad de explotación.

La puntuación CVSS se calcula a partir de tres métricas principales:

Métricas Base: Evalúan las características fundamentales de la vulnerabilidad, como su impacto en la confidencialidad, integridad y disponibilidad, así como la facilidad con que puede ser explotada.
Métricas Temporal: Consideran factores que pueden cambiar con el tiempo, como la disponibilidad de parches o la efectividad de las mitigaciones.
Métricas de Entorno: Permiten personalizar la puntuación en función de las características y configuraciones específicas del entorno en el que se encuentra la vulnerabilidad.

<h2 style="text-align:center">3. Priorización de Vulnerabilidades en un Entorno DevSecOps </h2>

En un entorno DevSecOps, la integración continua y la entrega continua (CI/CD) permiten a los desarrolladores y a los equipos de operaciones desplegar código de forma rápida y eficiente. Sin embargo, este ritmo acelerado aumenta la complejidad de gestionar las vulnerabilidades de seguridad, ya que las actualizaciones y cambios son constantes. Aquí es donde CVSS juega un papel fundamental al proporcionar una puntuación objetiva que ayuda a los equipos a tomar decisiones informadas.

La priorización de vulnerabilidades en DevSecOps implica tres pasos principales:

> - Identificación de vulnerabilidades: Usando herramientas de análisis estático y dinámico de código, así como de escaneo de dependencias, se detectan vulnerabilidades en las aplicaciones y sistemas.
> - Evaluación de las vulnerabilidades: Utilizando el CVSS, se calcula la puntuación de cada vulnerabilidad identificada en función de su gravedad.
> - Priorización y Remediación: Una vez evaluadas las vulnerabilidades, los equipos de DevSecOps deben priorizarlas en función de varios factores, incluidos la gravedad (puntuación CVSS), el impacto en la infraestructura, la facilidad de explotación y la criticidad para el negocio.





<br></br>

--
<br></br>

### Paso 1 :white_check_mark:

> - se crea el repositorio de la aplicación 

![image](https://github.com/user-attachments/assets/4638c2b7-d278-4a5b-9ec9-84bed411786f)

---

<br></br>


### Paso 2 :white_check_mark:

> - código de la aplicación 

![image](https://github.com/user-attachments/assets/26e881e8-44ea-4696-a30e-9c07e4575c12)


---

<br></br>


### Paso 3 :white_check_mark:

> - Aplicación corriendo en local 

![image](https://github.com/user-attachments/assets/8aceca9d-65b2-40e3-8702-f0629cdbca1a)


---

<br></br>



### Paso 4 :white_check_mark:

> - entramos a la consola de snyk  

![image](https://github.com/user-attachments/assets/c9488861-b77c-40d9-a4ae-a0d50b31777b)
![image](https://github.com/user-attachments/assets/b8560979-388d-49be-a334-11fda41bcd7e)

---

<br></br>


### Paso 5 :white_check_mark:

> - Vulnerabilidades.

![image](https://github.com/user-attachments/assets/649defee-091a-4c7b-8d88-7abd56225562)


![image](https://github.com/user-attachments/assets/31dc8d8d-919c-4fc2-b5e2-8165ce3b1a55)


---

<br></br>


### Paso 6 :white_check_mark:

> - https://cwe.mitre.org/data/definitions/78.html 
![image](https://github.com/user-attachments/assets/c2c7bd9f-b356-4147-b76c-12b9e61ea8e1)


---

<br></br>


### Paso 7 :white_check_mark:

> - Lista priorizada.

![image](https://github.com/user-attachments/assets/602b1153-3745-42b2-8de2-d3552e40b643)


---

<br></br>


### Paso 8 :white_check_mark:

> - Instalamos nmap desde py para la evaluacion cvss3 
![image](https://github.com/user-attachments/assets/5862b5ae-1105-46eb-be46-d8b44287249a)


---

<br></br>


### Paso 9 :white_check_mark:

> - Creamos el archivo de configuración para el escaneo 

![image](https://github.com/user-attachments/assets/5ea2a14a-87ba-49c6-8fa2-5b4b517d135b)

---

<br></br>


### Paso 10 :white_check_mark:

> - Creamos el docker para correr

![image](https://github.com/user-attachments/assets/026bc50b-80b4-4a2e-b8b7-b5f7c259473f)



---

<br></br>





### Paso 11 :white_check_mark:

> - Construimos la imagen.

    
![image](https://github.com/user-attachments/assets/7f7b8f4e-b45c-4136-8182-d68979d071d2)


---

<br></br>


### Paso 12 :white_check_mark:

> - Ejecutamos el contenedor


![image](https://github.com/user-attachments/assets/fc34b0de-f13b-4b5e-9256-a1a5c685d58e)


---

<br></br>

### Paso 13 :white_check_mark:

> - Configuramos la ruta del contenedor a escanear
![image](https://github.com/user-attachments/assets/b36ebc5f-bfb0-4dba-ab8a-6f47dd7cdd04)


https://github.com/acortes2/examen_devsecops













