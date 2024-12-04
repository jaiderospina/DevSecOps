### Integrantes:
- **Maria Mahecha**
- **Paola Lara**
- **Gustavo Ladino**
- **Yaneth Rodríguez**

 ## **Exámen Final**  
 
**Evaluación y Priorización de Vulnerabilidades en un Entorno DevSecOps mediante CVSS 4.0**

## Gestión de Vulnerabilidades

La gestión de vulnerabilidades es un proceso crítico en la ciberseguridad que implica la identificación, evaluación, tratamiento y mitigación de vulnerabilidades en sistemas y aplicaciones. En un entorno tecnológico en constante evolución, donde las amenazas son cada vez más sofisticadas y las brechas de seguridad pueden resultar en pérdidas significativas para las organizaciones, la gestión efectiva de vulnerabilidades se convierte en una prioridad estratégica.
Este proceso abarca varias etapas, comenzando con la identificación de vulnerabilidades a través de herramientas de análisis de seguridad, como SAST (Static Application Security Testing) y DAST (Dynamic Application Security Testing). Estas herramientas permiten detectar debilidades en el código fuente y en la configuración de la infraestructura, proporcionando información valiosa sobre posibles vectores de ataque.


## Evaluación de Vulnerabilidades con CVSS 4.0
La evaluación de vulnerabilidades es un componente fundamental en la gestión de la seguridad de la información, y el uso de un sistema estandarizado como el Common Vulnerability Scoring System (CVSS) proporciona un marco coherente y comprensible para medir la gravedad de las vulnerabilidades. La versión más reciente, CVSS 4.0, introduce mejoras significativas en la forma en que se evalúan y priorizan las vulnerabilidades, adaptándose a las necesidades cambiantes del panorama de amenazas actual.

### 1. Componentes de CVSS 4.0
CVSS 4.0 se compone de tres grupos principales de métricas: Métricas Base, Métricas Temporales y Métricas Ambientales. Cada uno de estos grupos proporciona una perspectiva diferente sobre la vulnerabilidad y su impacto potencial.

•	Métricas Base: Estas métricas representan las características intrínsecas de la vulnerabilidad que son constantes a lo largo del tiempo y en diferentes entornos. Incluyen:

•	Vector de Ataque (AV): Describe cómo un atacante puede explotar la vulnerabilidad (local, adyacente, red).

•	Complejidad del Ataque (AC): Evalúa la dificultad para explotar la vulnerabilidad.

•	Privilegios Requeridos (PR): Indica si se requieren privilegios para llevar a cabo el ataque.

•	Interacción del Usuario (UI): Determina si se necesita la interacción del usuario para explotar la vulnerabilidad.

•	Impacto (I): Evalúa el efecto en la confidencialidad, integridad y disponibilidad si se explota la vulnerabilidad.

El proceso de evaluación de vulnerabilidades con CVSS 4.0 implica varios pasos:

 1.	Identificación de Vulnerabilidades: Utilizar herramientas de análisis de seguridad (SAST, DAST, escáneres de dependencias) para identificar vulnerabilidades en el código, configuraciones y dependencias.
 2.	Asignación de Métricas Base: Evaluar cada vulnerabilidad identificada y asignar puntuaciones a las métricas base. Esto incluye determinar el vector de ataque, la complejidad del ataque, los privilegios requeridos, la interacción del usuario y el impacto en la confidencialidad, integridad y disponibilidad.
 3.	Evaluación de Métricas Temporales y Ambientales: Considerar factores temporales (como la disponibilidad de parches) y ajustar la puntuación de acuerdo con el contexto de la organización (por ejemplo, la criticidad de los activos afectados).
 4.	Cálculo de la Puntuación CVSS: Utilizar una calculadora CVSS para calcular la puntuación final, que puede oscilar entre 0.0 (sin riesgo) y 10.0 (riesgo crítico).
 5.	Documentación y Reporte: Documentar las vulnerabilidades evaluadas, sus puntuaciones CVSS y cualquier recomendación para mitigación. Esto es crucial para la priorización y el seguimiento de las acciones correctivas.

## 3. Priorización de Vulnerabilidades
Una vez que se han evaluado las vulnerabilidades utilizando CVSS 4.0, es posible priorizarlas de manera efectiva. Las vulnerabilidades con puntuaciones más altas deben ser abordadas primero, especialmente aquellas que afectan activos críticos o que tienen un impacto significativo en la organización. Además, el contexto empresarial y la criticidad del sistema afectado deben ser considerados al priorizar las acciones de remediación.

## 4. Beneficios de CVSS 4.0
 •	Consistencia: Proporciona un enfoque estandarizado para evaluar vulnerabilidades, lo que facilita la comunicación y la comprensión entre equipos técnicos y de gestión.
 
 •	Adaptabilidad: La inclusión de métricas temporales y ambientales permite a las organizaciones ajustar la evaluación según su contexto específico.
 
 •	Mejora Continua: Al integrar CVSS 4.0 en el ciclo de vida de desarrollo de software y la gestión de vulnerabilidades, las organizaciones pueden mejorar continuamente su postura de seguridad y respuesta a incidentes.

# Desarrollo de la actividad.

## 1)	Crear un repositorio en GitHub, que contenga una aplicación web básica

![imagen](https://github.com/user-attachments/assets/19ab482b-08b0-4c49-bfbb-e961e1316f17)

## 2)	Identificación de Vulnerabilidades:
Snyk es una herramienta de seguridad diseñada para ayudar a los desarrolladores a identificar y remediar vulnerabilidades en sus aplicaciones, especialmente en el código abierto y las dependencias. Se utiliza en la gestión de vulnerabilidades de las siguientes maneras:
 1.	Escaneo de Código y Dependencias - Snyk permite a los desarrolladores escanear su código y las dependencias de sus aplicaciones en busca de vulnerabilidades conocidas. Esto incluye soporte para varios lenguajes de programación.

Beneficios de Usar Snyk
•	Aumento de la Seguridad:
Ayuda a las organizaciones a mejorar la seguridad de sus aplicaciones al identificar y remediar vulnerabilidades de manera proactiva.

•	Eficiencia en el Desarrollo:
	Al integrar la seguridad en el proceso de desarrollo, Snyk permite a los equipos trabajar de manera más eficiente, reduciendo el tiempo dedicado a la gestión de vulnerabilidades.
 
•	Facilitación de la Cumplimentación Normativa:
Contribuye a cumplir con regulaciones y estándares de seguridad al proporcionar un enfoque estructurado para la gestión de vulnerabilidades.

## Beneficios de Usar Snyk

•	Aumento de la Seguridad:
Ayuda a las organizaciones a mejorar la seguridad de sus aplicaciones al identificar y remediar vulnerabilidades de manera proactiva.

•	Eficiencia en el Desarrollo:
Al integrar la seguridad en el proceso de desarrollo, Snyk permite a los equipos trabajar de manera más eficiente, reduciendo el tiempo dedicado a la gestión de vulnerabilidades.

•	Facilitación de la Cumplimentación Normativa:
Contribuye a cumplir con regulaciones y estándares de seguridad al proporcionar un enfoque estructurado para la gestión de vulnerabilidades.


### 1.	Escaneo de Código y Dependencias - Snyk permite a los desarrolladores escanear su código y las dependencias de sus aplicaciones en busca de vulnerabilidades conocidas. Esto incluye soporte para varios lenguajes de programación.
Beneficios de Usar Snyk
•	Aumento de la Seguridad:
Ayuda a las organizaciones a mejorar la seguridad de sus aplicaciones al identificar y remediar vulnerabilidades de manera proactiva.

•	Eficiencia en el Desarrollo:
Al integrar la seguridad en el proceso de desarrollo, Snyk permite a los equipos trabajar de manera más eficiente, reduciendo el tiempo dedicado a la gestión de vulnerabilidades.

•	Facilitación de la Cumplimentación Normativa:
Contribuye a cumplir con regulaciones y estándares de seguridad al proporcionar un enfoque estructurado para la gestión de vulnerabilidades.

# Ejecutar herramientas de análisis de seguridad

![imagen](https://github.com/user-attachments/assets/05baaa99-a24e-46f8-9bdf-89b13c71caf2)

![imagen](https://github.com/user-attachments/assets/2831453c-c785-43b1-8940-2745b2e50730)


### Evaluación con CVSS 4.0:
•	Asignar puntuaciones CVSS 4.0 a las vulnerabilidades identificadas considerando los nuevos factores de impacto, métricas ambientales y temporales.

![image](https://github.com/user-attachments/assets/5d54494f-01a2-4b19-ab47-b583d6cbff6b)

![image](https://github.com/user-attachments/assets/31243a1f-0e6a-4a48-a291-f3cf097f829c)

![image](https://github.com/user-attachments/assets/6f8caf23-fe17-43c2-b251-fc743a9eda11)

•	Priorización:
Crear una lista priorizada de las vulnerabilidades más críticas, justificando las decisiones con base en el contexto empresarial (disponibilidad, impacto en datos críticos, etc.)vulnerabilidades encontradas con detalles clave (vector, alcance, etc.)

![image](https://github.com/user-attachments/assets/104392fd-6b88-486c-b5ce-6e4b450c5c92)

![image](https://github.com/user-attachments/assets/59a7a104-778f-4235-b7a0-c6c9b1e2f489)

![image](https://github.com/user-attachments/assets/2ef4ee4f-59ab-4edb-8b17-cf520b3a629f)

![image](https://github.com/user-attachments/assets/271fb938-682a-4399-8f03-3558b5a3aeee)

**Simulación de vulnerabilidades:** Puedes introducir vulnerabilidades conocidas en tu código.

![image](https://github.com/user-attachments/assets/397ede83-343e-49f1-9dc7-6b54d97895ca)

![image](https://github.com/user-attachments/assets/4aca0f68-b615-4014-8604-65d88ba04761)

![image](https://github.com/user-attachments/assets/25703c80-95d9-4889-90dd-6e36f2437812)

![image](https://github.com/user-attachments/assets/cb46b4f4-6aa6-4b03-b49b-1024011ee832)

![image](https://github.com/user-attachments/assets/faba8557-ebff-444a-ae81-5ae0a49f0f86)

![image](https://github.com/user-attachments/assets/21a15588-942f-4e67-ae7c-5d4f8f473b41)

![image](https://github.com/user-attachments/assets/4812d7c4-5807-48e8-8cb3-e8032c93a3ad)

![image](https://github.com/user-attachments/assets/034accf4-e389-49a9-8cf9-364c29761ade)

**Snyk** es una herramienta esencial para los desarrolladores que buscan asegurar sus aplicaciones y dependencias de código abierto. Su capacidad para escanear, monitorear y remediar vulnerabilidades de manera eficiente la convierte en una solución valiosa en el panorama actual de la seguridad de software.

### Integración en DevSecOps
Para la integración utilizamos la herramienta JENKINS.

**Jenkins** es una herramienta de integración continua y entrega continua (CI/CD) de código abierto utilizada principalmente en el desarrollo de software. Su principal función es automatizar el proceso de desarrollo, permitiendo la integración continua de código y la entrega continua de aplicaciones a través de pipelines de automatización.

Realizamos Los  siguientes paso para la integración de JENKINS con el repositorio Github.

- En panel de control seleccionamos la opción de nueva tarea para empezar la creación de la tarea a ejecutar.

- ![image](https://github.com/user-attachments/assets/855b6f8e-b7d2-4f4d-8e25-7234f19126bf)

Se realiza la configuración para la integración con el repositorio de github. Donde se evidencia el repository URL.

![image](https://github.com/user-attachments/assets/8c2b0c32-288f-4880-a160-7e5b5eb065b1)
![image](https://github.com/user-attachments/assets/fd68c37c-d6d2-4bef-b722-f0f3d672c5b6)

![image](https://github.com/user-attachments/assets/0f77c524-2926-4fb3-b977-8bbff295f2b5)

![image](https://github.com/user-attachments/assets/fdbfb180-acca-4518-9f6d-20ab4a31dc82)

Se evidencia la creación de  la tarea examen final.

![image](https://github.com/user-attachments/assets/a42b5111-aa0c-4816-b62d-cc36c82d9e94)

Cuando se realiza commit el repositorio de github, en la pestaña cambios dentro de la tarea se puede evidenciar  un reporte de cada modificación realizada.

![image](https://github.com/user-attachments/assets/a1851da2-8f35-488b-a34f-746ecfe6000f)

![image](https://github.com/user-attachments/assets/dde11de4-f732-42ec-8da6-ec18c9aa3de5)

Se hace click en githubweb, y redirecciona al repositorio de github mostrando ( en color verde) el commit realizado.

![image](https://github.com/user-attachments/assets/eff208d5-22f1-451a-845e-d3eb9313d3d0)

Cuando se  realiza la creación de la tarea, automáticamente se genera una carpeta local donde se descarga el repositorio que se esta integrando con Jenkins.

![image](https://github.com/user-attachments/assets/5983b5ea-6f71-438f-8b11-5eaa71b1c16c)


































