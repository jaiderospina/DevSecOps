## Escaner de Vulnerabilidades

**OpenVAS (Open Vulnerability Assessment System)**.

Descripción funcional y operativa de OpenVAS
1. Descripción general: OpenVAS (Open Vulnerability Assessment System) es una herramienta de código abierto diseñada para realizar análisis de vulnerabilidades en redes y sistemas. Forma parte del framework Greenbone Vulnerability Management (GVM) y se utiliza principalmente para identificar, clasificar y mitigar vulnerabilidades de seguridad en entornos de TI. Es altamente personalizable y adecuada para entornos corporativos, gubernamentales o académicos.

2. Funcionalidad clave:
Escaneo de vulnerabilidades: OpenVAS realiza análisis detallados para detectar fallos de seguridad en sistemas operativos, aplicaciones, dispositivos de red y configuraciones. Utiliza una base de datos de vulnerabilidades conocida como Network Vulnerability Tests (NVTs).

Gestión de informes: Genera informes claros y personalizables que contienen el estado de seguridad del entorno analizado, incluyendo detalles sobre vulnerabilidades críticas, medias y bajas.

Detección de configuraciones erróneas: Identifica configuraciones débiles o incorrectas que pueden ser aprovechadas por atacantes, como contraseñas por defecto o puertos abiertos innecesarios.

Integración y escalabilidad: OpenVAS puede integrarse con herramientas de gestión de seguridad (SIEM) o flujos de trabajo existentes para permitir una respuesta rápida a incidentes. Además, es escalable, permitiendo gestionar entornos pequeños o grandes.

Actualización continua: La base de datos de vulnerabilidades se actualiza regularmente para incluir nuevos vectores de ataque y corregir falsos positivos o negativos.

3. Descripción operativa:
El proceso operativo de OpenVAS incluye las siguientes etapas:

a. Instalación:
Se instala como parte del GVM o como un servicio independiente.
Requiere un servidor configurado con las dependencias necesarias (habitualmente Linux).
b. Configuración:
Se define el ámbito de los escaneos, incluyendo rangos de IP, sistemas específicos o redes completas.
Permite establecer credenciales para escaneos autenticados (para análisis más profundos).
c. Ejecución de escaneos:
Los usuarios configuran tareas de escaneo desde la interfaz gráfica o la línea de comandos.
OpenVAS realiza un análisis pasivo y activo, verificando servicios, aplicaciones y configuraciones expuestas.
d. Análisis de resultados:
Los resultados incluyen una lista priorizada de vulnerabilidades, basada en métricas como el CVSS (Common Vulnerability Scoring System).
Las vulnerabilidades detectadas se clasifican en función de su criticidad.
e. Mitigación y remediación:
El usuario puede utilizar las recomendaciones de OpenVAS para parchear sistemas, reforzar configuraciones o eliminar servicios innecesarios.
f. Revisión continua:
Se pueden programar escaneos periódicos para garantizar una evaluación continua del estado de seguridad.
4. Casos de uso típicos:
Auditorías de seguridad internas: Evaluar la exposición a riesgos antes de una auditoría oficial.

Cumplimiento normativo: Demostrar conformidad con estándares como ISO 27001, GDPR, PCI DSS, entre otros.

Respuesta a incidentes: Identificar posibles puntos de entrada utilizados en un ataque.

Pruebas de aceptación de sistemas: Validar que los sistemas nuevos no introduzcan vulnerabilidades en la infraestructura.

5. Limitaciones:
Falsos positivos y negativos: Aunque OpenVAS es robusto, ningún escáner es perfecto. Requiere validación manual en algunos casos.

Carga en sistemas: Los escaneos intensivos pueden consumir recursos significativos en redes o dispositivos.

Curva de aprendizaje: La configuración inicial y la interpretación de resultados pueden ser complejas para usuarios no familiarizados con seguridad informática.


##  TALLER EN CLASE

En los trabajos de grupo habitual; 

1. Crear un contenedor de Openvas según se indica en https://greenbone.github.io/docs/latest/22.4/container/index.html .

2. Actualizar el contenedor creado con el motor de base de datos de vulnerabilidades. 

3. Descargar un contenedor vulnerable desde dockerhub y realizar un escaneo de vulnerabilidades al mismo.

5. Documentar el proceso.

6. Subir la imágen a dockerhub.

7. Documentar en el "overview" de dockerhub y en github ampliamente el proceso, en una carpeta titulada GrupoX y siguiendo las directrices ya dadas en clase.

Con aprecio; 

Jaider Ospina Navas.


