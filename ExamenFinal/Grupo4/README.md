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

## Gestión de Vulnerabilidades

La gestión de vulnerabilidades es un proceso crítico en la ciberseguridad que implica la identificación, evaluación, tratamiento y mitigación de vulnerabilidades en sistemas y aplicaciones. En un entorno tecnológico en constante evolución, donde las amenazas son cada vez más sofisticadas y las brechas de seguridad pueden resultar en pérdidas significativas para las organizaciones, la gestión efectiva de vulnerabilidades se convierte en una prioridad estratégica.
Este proceso abarca varias etapas, comenzando con la identificación de vulnerabilidades a través de herramientas de análisis de seguridad, como SAST (Static Application Security Testing) y DAST (Dynamic Application Security Testing). Estas herramientas permiten detectar debilidades en el código fuente y en la configuración de la infraestructura, proporcionando información valiosa sobre posibles vectores de ataque.

## Gestión de Vulnerabilidades

La gestión de vulnerabilidades es un proceso crítico en la ciberseguridad que implica la identificación, evaluación, tratamiento y mitigación de vulnerabilidades en sistemas y aplicaciones. En un entorno tecnológico en constante evolución, donde las amenazas son cada vez más sofisticadas y las brechas de seguridad pueden resultar en pérdidas significativas para las organizaciones, la gestión efectiva de vulnerabilidades se convierte en una prioridad estratégica.
Este proceso abarca varias etapas, comenzando con la identificación de vulnerabilidades a través de herramientas de análisis de seguridad, como SAST (Static Application Security Testing) y DAST (Dynamic Application Security Testing). Estas herramientas permiten detectar debilidades en el código fuente y en la configuración de la infraestructura, proporcionando información valiosa sobre posibles vectores de ataque.

## Evaluación de Vulnerabilidades con CVSS 4.0
La evaluación de vulnerabilidades es un componente fundamental en la gestión de la seguridad de la información, y el uso de un sistema estandarizado como el Common Vulnerability Scoring System (CVSS) proporciona un marco coherente y comprensible para medir la gravedad de las vulnerabilidades. La versión más reciente, CVSS 4.0, introduce mejoras significativas en la forma en que se evalúan y priorizan las vulnerabilidades, adaptándose a las necesidades cambiantes del panorama de amenazas actual.

## 1. Componentes de CVSS 4.0
CVSS 4.0 se compone de tres grupos principales de métricas: Métricas Base, Métricas Temporales y Métricas Ambientales. Cada uno de estos grupos proporciona una perspectiva diferente sobre la vulnerabilidad y su impacto potencial.
### •	Métricas Base: Estas métricas representan las características intrínsecas de la vulnerabilidad que son constantes a lo largo del tiempo y en diferentes entornos. Incluyen:
### •	Vector de Ataque (AV): Describe cómo un atacante puede explotar la vulnerabilidad (local, adyacente, red).
###•	Complejidad del Ataque (AC): Evalúa la dificultad para explotar la vulnerabilidad.
###•	Privilegios Requeridos (PR): Indica si se requieren privilegios para llevar a cabo el ataque.
###•	Interacción del Usuario (UI): Determina si se necesita la interacción del usuario para explotar la vulnerabilidad.
###•	Impacto (I): Evalúa el efecto en la confidencialidad, integridad y disponibilidad si se explota la vulnerabilidad.

El proceso de evaluación de vulnerabilidades con CVSS 4.0 implica varios pasos:

### 1.	Identificación de Vulnerabilidades: Utilizar herramientas de análisis de seguridad (SAST, DAST, escáneres de dependencias) para identificar vulnerabilidades en el código, configuraciones y dependencias.
### 2.	Asignación de Métricas Base: Evaluar cada vulnerabilidad identificada y asignar puntuaciones a las métricas base. Esto incluye determinar el vector de ataque, la complejidad del ataque, los privilegios requeridos, la interacción del usuario y el impacto en la confidencialidad, integridad y disponibilidad.
### 3.	Evaluación de Métricas Temporales y Ambientales: Considerar factores temporales (como la disponibilidad de parches) y ajustar la puntuación de acuerdo con el contexto de la organización (por ejemplo, la criticidad de los activos afectados).
### 4.	Cálculo de la Puntuación CVSS: Utilizar una calculadora CVSS para calcular la puntuación final, que puede oscilar entre 0.0 (sin riesgo) y 10.0 (riesgo crítico).
### 5.	Documentación y Reporte: Documentar las vulnerabilidades evaluadas, sus puntuaciones CVSS y cualquier recomendación para mitigación. Esto es crucial para la priorización y el seguimiento de las acciones correctivas.
### 3. Priorización de Vulnerabilidades
Una vez que se han evaluado las vulnerabilidades utilizando CVSS 4.0, es posible priorizarlas de manera efectiva. Las vulnerabilidades con puntuaciones más altas deben ser abordadas primero, especialmente aquellas que afectan activos críticos o que tienen un impacto significativo en la organización. Además, el contexto empresarial y la criticidad del sistema afectado deben ser considerados al priorizar las acciones de remediación.

## 2. Beneficios de CVSS 4.0
### •	Consistencia: Proporciona un enfoque estandarizado para evaluar vulnerabilidades, lo que facilita la comunicación y la comprensión entre equipos técnicos y de gestión.
### •	Adaptabilidad: La inclusión de métricas temporales y ambientales permite a las organizaciones ajustar la evaluación según su contexto específico.
### •	Mejora Continua: Al integrar CVSS 4.0 en el ciclo de vida de desarrollo de software y la gestión de vulnerabilidades, las organizaciones pueden mejorar continuamente su postura de seguridad y respuesta a incidentes.

# Desarrollo de la actividad.

## 1)	Crear un repositorio en GitHub, que contenga una aplicación web básica

![imagen](https://github.com/user-attachments/assets/19ab482b-08b0-4c49-bfbb-e961e1316f17)

## 2)	Identificación de Vulnerabilidades:
Snyk es una herramienta de seguridad diseñada para ayudar a los desarrolladores a identificar y remediar vulnerabilidades en sus aplicaciones, especialmente en el código abierto y las dependencias. Se utiliza en la gestión de vulnerabilidades de las siguientes maneras:
### 1.	Escaneo de Código y Dependencias - Snyk permite a los desarrolladores escanear su código y las dependencias de sus aplicaciones en busca de vulnerabilidades conocidas. Esto incluye soporte para varios lenguajes de programación.
### Beneficios de Usar Snyk
•	Aumento de la Seguridad:
•	Ayuda a las organizaciones a mejorar la seguridad de sus aplicaciones al identificar y remediar vulnerabilidades de manera proactiva.
•	Eficiencia en el Desarrollo:
•	Al integrar la seguridad en el proceso de desarrollo, Snyk permite a los equipos trabajar de manera más eficiente, reduciendo el tiempo dedicado a la gestión de vulnerabilidades.
•	Facilitación de la Cumplimentación Normativa:
## 2)	Identificación de Vulnerabilidades:
Snyk es una herramienta de seguridad diseñada para ayudar a los desarrolladores a identificar y remediar vulnerabilidades en sus aplicaciones, especialmente en el código abierto y las dependencias. Se utiliza en la gestión de vulnerabilidades de las siguientes maneras:

### 1.	Escaneo de Código y Dependencias - Snyk permite a los desarrolladores escanear su código y las dependencias de sus aplicaciones en busca de vulnerabilidades conocidas. Esto incluye soporte para varios lenguajes de programación.
Beneficios de Usar Snyk
•	Aumento de la Seguridad:
•	Ayuda a las organizaciones a mejorar la seguridad de sus aplicaciones al identificar y remediar vulnerabilidades de manera proactiva.
•	Eficiencia en el Desarrollo:
•	Al integrar la seguridad en el proceso de desarrollo, Snyk permite a los equipos trabajar de manera más eficiente, reduciendo el tiempo dedicado a la gestión de vulnerabilidades.
•	Facilitación de la Cumplimentación Normativa:
•	Contribuye a cumplir con regulaciones y estándares de seguridad al proporcionar un enfoque estructurado para la gestión de vulnerabilidades.

# Ejecutar herramientas de análisis de seguridad

![imagen](https://github.com/user-attachments/assets/05baaa99-a24e-46f8-9bdf-89b13c71caf2)

![imagen](https://github.com/user-attachments/assets/2831453c-c785-43b1-8940-2745b2e50730)












