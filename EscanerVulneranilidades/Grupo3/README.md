## Taller Escaner Vulneravilidades

## Integrantes Grupo


> - Ingrid Paola Quiroga
> - Juan Alvarez
> - Brayan Hernandez
> - Monica Florez Mejia
> - Alejandro Cortes
> - Charles Guerrero
 
## QUE ES OPEN V

OpenVAS (Open Vulnerability Assessment System) es una plataforma de código abierto diseñada para realizar evaluaciones de seguridad y auditorías de vulnerabilidades en sistemas informáticos. Es una herramienta integral que permite identificar posibles debilidades en redes, aplicaciones, servicios y dispositivos mediante el análisis de vulnerabilidades conocidas.

Características principales de OpenVAS:
Escaneo de Vulnerabilidades: OpenVAS realiza escaneos de seguridad completos en dispositivos y redes, buscando vulnerabilidades que puedan ser explotadas por atacantes. Utiliza una base de datos actualizada de más de 50,000 pruebas de vulnerabilidad (conocidas como "checks").

Interfaz de Usuario: OpenVAS proporciona una interfaz gráfica (usualmente a través de Greenbone Security Assistant, GSA) que permite gestionar y visualizar los resultados de los escaneos de forma sencilla.

Configuración Personalizada: Permite configurar escaneos con distintos niveles de profundidad y seleccionar los tipos de vulnerabilidades a buscar. Los usuarios pueden crear políticas personalizadas para adaptarse a las necesidades específicas de seguridad de su infraestructura.

Base de Datos de Vulnerabilidades: Se actualiza constantemente con nuevas vulnerabilidades y exploits, gracias a la comunidad de seguridad y los desarrolladores del proyecto. Esta base de datos ayuda a identificar riesgos de seguridad actuales en los sistemas.

Informes Detallados: Después de un escaneo, OpenVAS genera informes detallados sobre las vulnerabilidades encontradas, incluyendo una clasificación por gravedad, descripción de la vulnerabilidad y recomendaciones para su mitigación o resolución.

Integración con otras Herramientas: OpenVAS puede ser integrado con otras herramientas de seguridad, como SIEMs (Security Information and Event Management) y sistemas de gestión de incidentes para mejorar la respuesta ante amenazas.

¿Qué es lo que evalúa?
OpenVAS puede escanear:

Redes: Detecta configuraciones incorrectas o vulnerabilidades en routers, switches y otros dispositivos de red.
Sistemas Operativos: Examina máquinas con sistemas operativos como Linux, Windows o macOS en busca de fallos de seguridad.
Aplicaciones Web y Servicios: Evalúa aplicaciones web, servidores web, bases de datos, y otros servicios en busca de vulnerabilidades.
Ventajas:
Código abierto y gratuito.
Actualizaciones frecuentes de vulnerabilidades.
Escaneo en profundidad y detallado.
Interfaz amigable para gestionar escaneos.
Desventajas:
Requiere configuración técnica. Aunque OpenVAS es poderoso, puede ser complejo de configurar y administrar para usuarios sin experiencia.
Rendimiento: Los escaneos muy grandes pueden ser lentos dependiendo de la infraestructura.
En resumen, OpenVAS es una herramienta robusta para la detección de vulnerabilidades, utilizada por profesionales de seguridad para mejorar la defensa de sistemas informáticos y redes mediante el análisis continuo de posibles debilidades.



Tú dijiste:
dame un resumen para un presentacion
ChatGPT Plus
ChatGPT
Aquí tienes un resumen para una presentación sobre OpenVAS:

¿Qué es OpenVAS?

OpenVAS (Open Vulnerability Assessment System) es una herramienta de código abierto utilizada para realizar evaluaciones de seguridad y escaneos de vulnerabilidades en sistemas informáticos, redes y aplicaciones. Su objetivo es identificar posibles debilidades y riesgos de seguridad que puedan ser explotados por atacantes.

Características clave:

Escaneo de Vulnerabilidades: OpenVAS realiza escaneos exhaustivos buscando vulnerabilidades conocidas en dispositivos, redes y aplicaciones.

Interfaz Gráfica: Ofrece una interfaz fácil de usar a través de Greenbone Security Assistant (GSA) para gestionar y visualizar los resultados de los escaneos.

Base de Datos Actualizada: OpenVAS cuenta con una extensa base de datos con más de 50,000 pruebas de vulnerabilidad, que se actualiza constantemente.

Informes Detallados: Genera informes completos sobre las vulnerabilidades encontradas, con clasificación por gravedad y recomendaciones de mitigación.

Configuración Personalizada: Permite realizar escaneos ajustados a las necesidades específicas del entorno, personalizando políticas y opciones de escaneo.

Ventajas de OpenVAS:

Gratuito y de código abierto.
Actualizaciones frecuentes para detectar vulnerabilidades nuevas.
Escaneos detallados y análisis profundo de la seguridad.
¿Para qué se utiliza?

Evaluación de redes: Identificar vulnerabilidades en routers, switches y dispositivos de red.
Auditoría de sistemas operativos: Analizar máquinas con sistemas como Linux, Windows o macOS.
Escaneo de aplicaciones web: Detectar fallos en servidores y aplicaciones web.
Conclusión:

OpenVAS es una herramienta esencial para la gestión de seguridad en infraestructuras IT, permitiendo detectar vulnerabilidades antes de que los atacantes puedan explotarlas. Es ideal para profesionales de seguridad que buscan una solución poderosa y gratuita para proteger sus sistemas y redes.

## PROCESO DE ESCANEO CON OPEN VAS

1. Creamos una carpeta y la abrimos con visual studio.  

con los presentes comandos descargamos el archivo docker-compose.yaml y lo corremos 
![image](https://github.com/user-attachments/assets/77e4f2e8-e449-4d59-aee4-7a54dae599db)


2. Acá visualizamos la descarga del archivo docker-compose.yml

![image](https://github.com/user-attachments/assets/8fba0da1-5939-4582-b5d0-e3d483d3eb9b)



3.aca verificamos la ejecucion de los contenedores  
![image](https://github.com/user-attachments/assets/ee04f7d1-f585-4288-aef0-3e55ace1e6fc)


4.ingresando a la url podemos visualizar es dashboard de openvas 

![image](https://github.com/user-attachments/assets/bb8e41ad-54d2-4aa6-8926-6f2d78239fa9)

![image](https://github.com/user-attachments/assets/389e1ac9-0e53-45fb-8d09-1810c8ec203d)

5.corremos el contenedor con vulnerabilidades

![image](https://github.com/user-attachments/assets/e03d9446-820d-44af-9312-55f31b7d5b1b)


Cuando escaneamos una vulnerabilidad con OpenVAS, el proceso implica varias etapas clave para detectar y evaluar posibles fallos de seguridad en el sistema objetivo. Aquí te explico qué sucede paso a paso durante el escaneo:

## 1. Inicio del Escaneo:
Configuración del Escaneo: Se configura el escaneo en OpenVAS, donde seleccionas el objetivo (la IP o rango de IPs), el tipo de escaneo y las políticas de seguridad (por ejemplo, si quieres realizar un escaneo rápido o profundo).
Selección de pruebas (NVTs): OpenVAS utiliza pruebas conocidas como NVTs (Network Vulnerability Tests), que son scripts diseñados para detectar vulnerabilidades específicas en servicios, aplicaciones y sistemas operativos. Estas pruebas están basadas en una base de datos de vulnerabilidades conocida y se actualizan frecuentemente.
## 2. Exploración de Servicios y Puertos:
Descubrimiento de Servicios: OpenVAS escanea los puertos abiertos del objetivo para identificar los servicios activos (como HTTP, FTP, SSH, bases de datos, etc.).
Identificación de Versiones: Una vez detectados los servicios, OpenVAS intenta identificar las versiones exactas de las aplicaciones y sistemas operativos en ejecución. Esto es crucial para detectar vulnerabilidades específicas relacionadas con una versión particular del software.
## 3. Ejecución de las Pruebas de Vulnerabilidades (NVTs):
Pruebas de Vulnerabilidad: OpenVAS ejecuta una serie de pruebas automatizadas en cada servicio y aplicación identificados. Estas pruebas buscan vulnerabilidades conocidas que puedan ser explotadas. Algunos ejemplos son:
Desbordamientos de búfer.
Fallas en la autenticación.
Inyección de comandos o SQL.
Configuraciones incorrectas de seguridad.
Comparación con Base de Datos de Vulnerabilidades: Cada NVT compara la información obtenida de los servicios y las configuraciones con su base de datos de vulnerabilidades conocida. Esto le permite identificar si una vulnerabilidad es relevante para el servicio o la versión del software.
## 4. Evaluación de la Severidad:
Clasificación de Vulnerabilidades: OpenVAS clasifica las vulnerabilidades detectadas según su gravedad, que puede ser:
Crítica (posibles exploits inmediatos, alto riesgo).
Alta (puede ser explotada, pero con menor impacto inmediato).
Media o Baja (requiere condiciones específicas para ser explotada o es de menor riesgo).
Impacto Potencial: Además de la severidad, OpenVAS evalúa el impacto potencial de la vulnerabilidad, indicando si puede comprometer la confidencialidad, integridad o disponibilidad del sistema.
## 5. Generación de Informes:
Informe de Resultados: Una vez que el escaneo ha terminado, OpenVAS genera un informe detallado que incluye:
Vulnerabilidades detectadas.
Descripción de cada vulnerabilidad.
Nivel de severidad.
Recomendaciones de mitigación o corrección (como actualizar una aplicación, cambiar configuraciones inseguras, etc.).
Opciones de Informe: Los informes pueden ser personalizados para incluir detalles específicos o para ser exportados en diferentes formatos (PDF, HTML, XML, etc.).
## 6. Acciones Posteriores:
Mitigación de Vulnerabilidades: Basado en los informes generados, los administradores de sistemas o equipos de seguridad deben tomar medidas correctivas, que pueden incluir:
Aplicación de parches de seguridad.
Modificación de configuraciones inseguras.
Desactivación de servicios no necesarios.
Re-escaneo: Después de aplicar las correcciones, es común realizar un nuevo escaneo para verificar que las vulnerabilidades hayan sido efectivamente solucionadas







