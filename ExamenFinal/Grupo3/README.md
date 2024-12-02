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

<h2 style="text-align:center"> Priorización de Vulnerabilidades en un Entorno DevSecOps </h2>

En un entorno DevSecOps, la integración continua y la entrega continua (CI/CD) permiten a los desarrolladores y a los equipos de operaciones desplegar código de forma rápida y eficiente. Sin embargo, este ritmo acelerado aumenta la complejidad de gestionar las vulnerabilidades de seguridad, ya que las actualizaciones y cambios son constantes. Aquí es donde CVSS juega un papel fundamental al proporcionar una puntuación objetiva que ayuda a los equipos a tomar decisiones informadas.

La priorización de vulnerabilidades en DevSecOps implica tres pasos principales:

> - Identificación de vulnerabilidades: Usando herramientas de análisis estático y dinámico de código, así como de escaneo de dependencias, se detectan vulnerabilidades en las aplicaciones y sistemas.
> - Evaluación de las vulnerabilidades: Utilizando el CVSS, se calcula la puntuación de cada vulnerabilidad identificada en función de su gravedad.
> - Priorización y Remediación: Una vez evaluadas las vulnerabilidades, los equipos de DevSecOps deben priorizarlas en función de varios factores, incluidos la gravedad (puntuación CVSS), el impacto en la infraestructura, la facilidad de explotación y la criticidad para el negocio.


<h2 style="text-align:center"> Aplicación de CVSS en la Priorización de Vulnerabilidades </h2>


 El uso de CVSS para priorizar vulnerabilidades en un entorno DevSecOps puede incluir los siguientes pasos detallados:

Recolección de Datos de Vulnerabilidades: Los equipos de DevSecOps deben integrar herramientas automatizadas de escaneo de seguridad (como Snyk, OWASP Dependency-Check, etc.) dentro de su pipeline CI/CD. Estas herramientas identifican vulnerabilidades en el código fuente y en las dependencias, proporcionando información sobre la severidad y el tipo de vulnerabilidad.

> - Cálculo de la Puntuación CVSS: Cada vulnerabilidad identificada debe ser evaluada utilizando la puntuación CVSS. Esto incluye la evaluación de los factores clave:
> - Impacto en la Confidencialidad, Integridad y Disponibilidad (C, I, A): Se evalúa el impacto directo en la seguridad del sistema. Si la vulnerabilidad afecta gravemente la confidencialidad, integridad o disponibilidad, recibirá una puntuación alta.
> - Complejidad de la Explotación (Exploitability): Se analiza cuán fácil es para un atacante explotar la vulnerabilidad. Si la explotación es sencilla, la puntuación CVSS será más alta.
> - Requerimientos de Autenticación: Determina si la vulnerabilidad puede ser explotada sin autenticación o si es necesario un acceso previo.
> - Contextualización con Métricas de Entorno: Una vez calculada la puntuación base, se pueden aplicar métricas de entorno que ajusten la gravedad en función de las características del entorno en el que la vulnerabilidad se encuentra. Esto incluye la exposición pública de la vulnerabilidad, la presencia de defensas adicionales o la criticidad de la infraestructura afectada.


<h2 style="text-align:center"> Estrategias de Priorización y Remediacións </h2>


La priorización de vulnerabilidades no solo depende de la puntuación CVSS, sino también de otros factores del entorno DevSecOps, tales como la criticidad del servicio afectado, el impacto en la experiencia del usuario y los recursos disponibles para la corrección.

Algunos enfoques clave para la remediación incluyen:
> - Automatización de la Remediación: En un entorno DevSecOps, la automatización es esencial para aplicar correcciones rápidamente. Las vulnerabilidades con puntuaciones CVSS más altas deben ser tratadas primero mediante parches automáticos o soluciones de mitigación.
> - Categorización por Impacto: Las vulnerabilidades de alto impacto en sistemas críticos deben ser priorizadas sobre las que afectan a componentes menos sensibles.
> - Integración con el Ciclo de Vida del Desarrollo: Los equipos deben integrar la gestión de vulnerabilidades en cada fase del ciclo de vida del desarrollo (planificación, codificación, pruebas, despliegue y mantenimiento) para detectar y corregir vulnerabilidades en tiempo real.


<h2 style="text-align:center"> Beneficios de Usar CVSS en DevSecOps </h2>

Al aplicar el CVSS en un entorno DevSecOps, las organizaciones pueden lograr varios beneficios:
> - Evaluación Objetiva de Riesgos: CVSS proporciona una puntuación estandarizada que permite a los equipos de desarrollo y operaciones tomar decisiones basadas en hechos, en lugar de en suposiciones o juicios subjetivos.
> - Priorización Eficiente: Las vulnerabilidades con mayor puntuación se pueden abordar con mayor rapidez, lo que reduce el riesgo general de explotación.
> - Transparencia y Colaboración: El uso de CVSS fomenta la comunicación y colaboración entre los equipos de seguridad, desarrollo y operaciones al proporcionar un marco común para la evaluación de vulnerabilidades.
> - Mejora Continua: Al integrar la gestión de vulnerabilidades y la puntuación CVSS en el ciclo de vida del desarrollo, las organizaciones pueden mejorar continuamente la seguridad de sus aplicaciones y sistemas, adaptándose rápidamente a nuevas amenazas.



<h2 style="text-align:center">Desafíos y Consideraciones</h2>

El uso de CVSS en DevSecOps ofrece importantes ventajas, también presenta algunos desafíos:
> - Dependencia de la Precisión de las Herramientas de Escaneo: Las herramientas de escaneo deben estar bien configuradas y mantenerse actualizadas para garantizar que las vulnerabilidades sean detectadas correctamente.
> - Sobrecarga de Vulnerabilidades de Baja Prioridad: Un exceso de vulnerabilidades de baja prioridad puede generar una sobrecarga de trabajo para los equipos, haciendo difícil centrarse en las vulnerabilidades críticas.
> - Manejo de Falsos Positivos: Las puntuaciones CVSS pueden no reflejar siempre el contexto completo de la vulnerabilidad, por lo que es importante realizar una revisión manual para asegurar que la prioridad sea correcta.









<br></br>


<br></br>

<h2 style="text-align:center">Proceso de evaluación y priorización</h2>

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

Snyk es una plataforma de seguridad enfocada en el análisis y la gestión de vulnerabilidades en aplicaciones, infraestructura y dependencias de código abierto. Está diseñada para ayudar a los equipos de desarrollo y operaciones (DevSecOps) a detectar, corregir y prevenir vulnerabilidades en el software de manera continua, integrándose de manera fluida en los flujos de trabajo de desarrollo ágil y DevOps.
aqui mostraremos el paso a paso de como se utilizo la herramienta
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













