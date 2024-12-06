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

En el siguiente informe se presentarán las imágenes y la información detallada sobre el escaneo de una vulnerabilidad, utilizando una aplicación llamada 

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

<h2 style="text-align:center">Soluciones implementadas para mitigar riesgos</h2>

Para Este proceso se utilizara la herramienta Snyk, una plataforma de seguridad especializada en el análisis y la gestión de vulnerabilidades en aplicaciones, infraestructuras y dependencias de código abierto. Diseñada para asistir a los equipos de desarrollo y operaciones (DevSecOps), Snyk permite detectar, corregir y prevenir vulnerabilidades en el software de manera continua, integrándose de forma fluida en los flujos de trabajo ágiles y DevOps


aqui mostraremos el paso a paso de como se utilizo la herramienta

> - Escaneo de vulnerabilidades: Snyk analiza tanto las dependencias de código abierto (como bibliotecas de JavaScript, Python, Java, Ruby, entre otros) como el código fuente, para identificar vulnerabilidades conocidas. También examina contenedores, infraestructura como código (IaC), y proyectos de infraestructura en la nube.
> - Integración en pipelines de CI/CD: Snyk se puede integrar fácilmente en los pipelines de integración continua y entrega continua (CI/CD), lo que permite a los equipos detectar vulnerabilidades en las primeras fases del desarrollo y corregirlas de forma ágil.
> - Base de datos de vulnerabilidades: Snyk utiliza una base de datos de vulnerabilidades que se actualiza constantemente, brindando a los desarrolladores información precisa y al día sobre los riesgos de seguridad.
> - Automatización de correcciones: Además de detectar vulnerabilidades, Snyk ofrece recomendaciones de corrección, incluyendo actualizaciones de dependencias y parches, y en algunos casos, puede realizar la corrección automáticamente.
> - Pruebas de código y contenedores: Snyk permite realizar pruebas de seguridad tanto en el código fuente como en las imágenes de contenedores, lo que ayuda a identificar configuraciones incorrectas o vulnerabilidades en tiempo de ejecución.

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

### Paso 14 :white_check_mark:

> - subimos la imagen a docker hub

https://github.com/acortes2/examen_devsecops

![image](https://github.com/user-attachments/assets/7061d87c-ddb6-4537-afdd-0783e08e2b0c)
![image](https://github.com/user-attachments/assets/c4144582-03d3-4e1c-840b-a35e04c002cf)


### Paso 15 :white_check_mark:

> - Escaneo de la aplicación

En una máquina virtual con kalilinux instalamos el openvas y corrimos en Docker la aplicación 

![image](https://github.com/user-attachments/assets/c000702d-a5e7-4a69-998e-cebcab1f575d)

![image](https://github.com/user-attachments/assets/58af2d91-3022-489c-b3b2-7c944a91b080)

![image](https://github.com/user-attachments/assets/118c09f7-4bff-4faa-a487-92e3f881a379)

![image](https://github.com/user-attachments/assets/33d8fb4b-c7d5-49e3-8ed4-386640f68dc5)

 ![image](https://github.com/user-attachments/assets/57d0baff-81c7-4612-8716-37e971e03f37)

### Paso 16 :white_check_mark: Se evidencia la Instalación Docker

![image](https://github.com/user-attachments/assets/3163dbb8-6465-4477-8514-60cb5a51c4b5)


Corremos la imagen previamente subida a Docker hub 
![image](https://github.com/user-attachments/assets/067c4a07-3ceb-4340-b083-968a93aa7502)

Verificamos la ejecución del Docker

![image](https://github.com/user-attachments/assets/17e870b1-0722-4b2d-bbb6-30ddd4c5ca5a)

![image](https://github.com/user-attachments/assets/c308b631-2ec8-4754-9ca7-cba675d491b4)

![image](https://github.com/user-attachments/assets/71b6280c-4854-4601-8504-be16f4e34f0b)

Verificamos los procesos corriendo en el SO
![image](https://github.com/user-attachments/assets/bacfb168-72b5-4395-ab25-c721ca157922)

Análisis de la aplicación

![image](https://github.com/user-attachments/assets/9eafa413-2f5d-4126-b5b5-290f712df142)

![image](https://github.com/user-attachments/assets/1f4d7610-d0d0-494f-817e-9cd5d94de94d)

![image](https://github.com/user-attachments/assets/c5f9765c-820f-4e8e-af8b-8b59bf6f2874)

![image](https://github.com/user-attachments/assets/1b59b060-4113-4a18-bae6-71fd325be8d6)

![image](https://github.com/user-attachments/assets/c7655777-66ab-40ba-a32c-a2cb1fdd1a73)

![image](https://github.com/user-attachments/assets/3624e43e-4d71-4743-a3da-df89d9f4309a)

![image](https://github.com/user-attachments/assets/c344f832-f635-4f1f-92cc-088df3a4be28)

![image](https://github.com/user-attachments/assets/bacb32a6-4c7a-4805-afb4-9ed47ad57896)

![image](https://github.com/user-attachments/assets/1cf93965-ca87-4305-be8b-1da6e701bc26)

![image](https://github.com/user-attachments/assets/4f3b33a6-b4dd-43a1-b189-ebbe2e557e7c)

![image](https://github.com/user-attachments/assets/66fec489-6a13-4348-ab1c-ebd05d062f13)

![image](https://github.com/user-attachments/assets/f8cbd81d-4442-41d1-81e5-966d9597ad70)

![image](https://github.com/user-attachments/assets/3e7f3706-4953-4979-ae28-c54767fb8fcf)

![image](https://github.com/user-attachments/assets/bc2b7113-07e1-45d2-a4af-640080ed96e4)

# CVE 1999-0524
El CVE-1999-0524 describe una vulnerabilidad relacionada con la configuración de SNMP (Simple Network Management Protocol). En términos generales, este CVE se refiere a la existencia de una comunidad predeterminada o débil configurada en dispositivos de red que utilizan SNMP, como "public" o "private". Estas comunidades actúan como contraseñas para acceder a información de administración del dispositivo, y si no se cambian de sus valores predeterminados, pueden ser explotadas fácilmente por atacantes.

> - Detalles clave:

•	Problema: Uso de comunidades SNMP predeterminadas o triviales.
•	Impacto: Acceso no autorizado a información sensible o incluso a la configuración del dispositivo de red.
•	Solución: Cambiar las comunidades SNMP predeterminadas por valores personalizados y robustos. Si SNMP no es necesario, deshabilitarlo para reducir la superficie de ataque.

> - Buenas prácticas para mitigar este tipo de vulnerabilidad:
1.	Usar SNMPv3: Las versiones anteriores como SNMPv1 y SNMPv2 son menos seguras, ya que no cifran los datos. SNMPv3 incluye cifrado y autenticación.
2.	Restringir el acceso: Configurar ACLs (listas de control de acceso) para limitar las direcciones IP desde las cuales se puede acceder al servicio SNMP.
3.	Supervisar logs: Monitorear los intentos de acceso y las configuraciones del dispositivo para detectar posibles intrusiones.
4.	Deshabilitar SNMP si no es necesario.
Esta vulnerabilidad tiene más de dos décadas, pero aún puede ser relevante si se usan dispositivos antiguos o configuraciones obsoletas en entornos modernos.4


# Comandos básicos de Linux

> - Navegación por el sistema de archivos

pwd - Muestra el directorio actual.

ls - Lista los archivos y directorios.

ls -l - Muestra detalles en formato largo.

ls -a - Incluye archivos ocultos

cd [ruta] - Cambia de directorio.

cd .. - Sube un nivel en el árbol de directorios.

cd / - Va al directorio raíz.

Gestión de archivos y directorios

touch [archivo] - Crea un archivo vacío.

mkdir [directorio] - Crea un directorio.

cp [origen] [destino] - Copia archivos o directorios.

cp -r - Copia recursivamente directorios.

mv [origen] [destino] - Mueve o renombra archivos.

rm [archivo] - Elimina archivos.

rm -r [directorio] - Elimina directorios recursivamente.

> - Visualización de archivos

cat [archivo] - Muestra el contenido de un archivo.

less [archivo] - Muestra el contenido de un archivo página por página.

head [archivo] - Muestra las primeras líneas de un archivo.

tail [archivo] - Muestra las últimas líneas de un archivo.

tail -f [archivo] - Sigue el crecimiento del archivo (útil para logs).


> - Gestión de procesos
> - 
ps - Muestra los procesos en ejecución.

ps aux - Lista todos los procesos con detalles.

top o htop - Monitoriza procesos en tiempo real.

kill [PID] - Finaliza un proceso por su ID.

killall [nombre] - Finaliza procesos por nombre.

> - Redes y conectividad

ifconfig o ip a - Muestra configuraciones de red

ping [host] - Verifica conectividad con un host.

curl [URL] - Realiza solicitudes HTTP.

wget [URL] - Descarga archivos desde una URL

> - Gestión de 

chmod [permisos] [archivo] - Cambia los permisos de un archivo.

chown [usuario:grupo] [archivo] - Cambia el propietario de un archivo.

> - Comandos básicos de Docker
Gestión de imágenes

docker pull [imagen] - Descarga una imagen del Docker Hub.

docker images - Lista las imágenes locales.

docker rmi [imagen] - Elimina una imagen.

> - Gestión de contenedores

docker ps - Lista los contenedores en ejecución.

docker ps -a - Incluye contenedores detenidos.

docker run [imagen] - Inicia un contenedor desde una imagen.

docker run -d [imagen] - Inicia un contenedor en segundo plano.

docker run -it [imagen] - Inicia un contenedor con acceso interactivo.

docker stop [ID/nombre] - Detiene un contenedor.

docker start [ID/nombre] - Inicia un contenedor detenido.

docker restart [ID/nombre] - Reinicia un contenedor.
docker rm [ID/nombre] - Elimina un contenedor.

> - Inspección y logs

docker logs [ID/nombre] - Muestra los logs de un contenedor.

docker logs -f [ID/nombre] - Sigue los logs en tiempo real.

docker inspect [ID/nombre] - Detalla la configuración de un contenedor o imagen.

docker exec [ID/nombre] [comando] - Ejecuta un comando dentro de un contenedor en ejecución.

docker exec -it [ID/nombre] /bin/bash - Abre una terminal interactiva.

> - Gestión de volúmenes y redes

docker volume ls - Lista los volúmenes.

docker volume rm [volumen] - Elimina un volumen.

docker network ls - Lista las redes.

docker network rm [red] - Elimina una red.

> - Limpieza
docker system prune - Elimina datos no utilizados (contenedores detenidos, redes, volúmenes, etc.).

docker system prune -a - Incluye imágenes no utilizadas.

























