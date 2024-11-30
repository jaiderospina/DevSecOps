**Análisis de Vulnerabilidades en el OWASP Top 10: Métodos de Explotación y Prevención**

# Taller OWASP

## Integrantes del Grupo 7

| Nombre      | Apellido     |
|-------------|--------------|
| Michelle    | Gutierrez    |
| Harold      | Ramirez      |
| Camilo      | Porras       |

**1. Control de Acceso Roto (Broken Access Control)**
   
**•	Descripción:** Se produce cuando los controles de acceso en la aplicación no están implementados correctamente, permitiendo que usuarios no autorizados accedan a funciones o datos restringidos.

**•	Métodos de Explotación:**

o	Manipulación de URLs: Los atacantes modifican parámetros en la URL para acceder a recursos restringidos.

o	Escalada de privilegios: Consiste en realizar acciones de usuarios con mayores permisos a través de accesos inadecuados.

o	Modificación de tokens de sesión: Mediante el uso de herramientas como Burp Suite, los atacantes interceptan y modifican tokens para obtener permisos elevados.

**•	Mejores Prácticas de Prevención:**

o	Implementar el principio de menor privilegio en todas las funciones.

o	Revisar y restringir los permisos en cada recurso de la aplicación.

o	Utilizar controles de acceso basados en roles (RBAC) y revisar regularmente los permisos de los usuarios.

**2. Inyección (Injection)**
   
**•	Descripción:** Ocurre cuando se permite la inserción de comandos maliciosos en el intérprete de la aplicación debido a una falta de validación o sanitización de datos.

**•	Métodos de Explotación:**

o	Inyección SQL: Los atacantes manipulan consultas SQL para acceder a datos sensibles o incluso obtener control de la base de datos.

o	Inyección de Comandos del Sistema Operativo: Permite a los atacantes ejecutar comandos en el servidor.

o	Herramientas comunes: SQLmap y Burp Suite para automatizar pruebas y ataques de inyección.

**•	Mejores Prácticas de Prevención:**

o	Utilizar consultas parametrizadas y procedimientos almacenados en lugar de construir SQL dinámico.

o	Validar y sanitizar todas las entradas del usuario para eliminar caracteres especiales.

o	Implementar un firewall de aplicaciones web (WAF) para detectar y bloquear ataques de inyección.

**3. Exposición de Datos Sensibles (Sensitive Data Exposure)**
   
**•	Descripción:** Esta vulnerabilidad surge cuando los datos confidenciales no están adecuadamente protegidos, exponiéndose en texto plano o sin cifrado.

**•	Métodos de Explotación:**

o	Interceptación de tráfico: Los atacantes pueden interceptar datos sensibles si no están cifrados (por ejemplo, mediante ataques Man-in-the-Middle).

o	Acceso directo a almacenamiento: Si los datos están en texto plano en el servidor, pueden ser leídos en caso de compromisos.

**•	Mejores Prácticas de Prevención:**

o	Usar protocolos seguros (HTTPS) para cifrar las comunicaciones.

o	Implementar un cifrado adecuado para datos en reposo y en tránsito.

o	Restringir el acceso a datos sensibles solo a usuarios autorizados.

**4. Inseguridad en el Diseño (Insecure Design)**
   
**•	Descripción:** Ocurre cuando no se consideran principios de seguridad en el diseño de la aplicación, abriendo brechas de seguridad desde el inicio.

**•	Métodos de Explotación:**

o	Manipulación de flujos de trabajo: Los atacantes explotan lógicas y flujos de trabajo mal diseñados para acceder a funciones sensibles.

o	Engaños en autenticación: Los flujos de autenticación mal diseñados pueden permitir eludir autenticaciones.

**•	Mejores Prácticas de Prevención:**

o	Incluir seguridad en todas las etapas del diseño y desarrollo de la aplicación.

o	Realizar modelado de amenazas para identificar posibles riesgos en el diseño.

o	Implementar pruebas de seguridad en la fase de diseño y desarrollo de la aplicación.

**5. Errores de Configuración de Seguridad (Security Misconfiguration)**
    
**•	Descripción:** Esta vulnerabilidad ocurre cuando las configuraciones de seguridad no están adecuadamente implementadas, exponiendo componentes a ataques.

**•	Métodos de Explotación:**

o	Exploración de puertos y servicios: Los atacantes pueden usar herramientas como Nmap para identificar servicios abiertos mal configurados.

o	Archivos de configuración expuestos: Archivos sensibles accesibles públicamente pueden revelar configuraciones críticas.

**•	Mejores Prácticas de Prevención:**

o	Deshabilitar los servicios y características no necesarias en el servidor.

o	Realizar revisiones y auditorías regulares de configuración.

o	Automatizar la gestión de configuraciones utilizando herramientas de seguridad de infraestructura como código.

**6. Componentes Vulnerables y Obsoletos (Vulnerable and Outdated Components)**
    
**•	Descripción:** Cuando se utilizan componentes desactualizados o sin parches, pueden existir vulnerabilidades conocidas que los atacantes aprovechan.

**•	Métodos de Explotación:**

o	Explotación de vulnerabilidades conocidas: Los atacantes aprovechan vulnerabilidades en componentes sin actualizar (Ej. CVEs conocidos).

o	Escaneo de aplicaciones: Herramientas como OWASP Dependency-Check permiten identificar componentes vulnerables en una aplicación.

**•	Mejores Prácticas de Prevención:**

o	Mantener los componentes de la aplicación actualizados y con los parches más recientes.

o	Implementar análisis de dependencias para identificar versiones inseguras.

o	Evitar el uso de componentes no soportados o que no reciban actualizaciones de seguridad.

**7. Control de Identidad y Autenticación Deficiente (Identification and Authentication Failures)**
    
**•	Descripción:** La autenticación inadecuada permite a los atacantes suplantar a otros usuarios o acceder a datos sin autorización.

**•	Métodos de Explotación:**

o	Ataques de fuerza bruta: Los atacantes intentan múltiples combinaciones de credenciales para obtener acceso.

o	Robo de tokens: Los tokens de autenticación inseguros o sin expiración permiten acceso prolongado.

**•	Mejores Prácticas de Prevención:**

o	Implementar autenticación multifactor (MFA) para añadir una capa de seguridad.

o	Utilizar tokens seguros y configurar tiempos de expiración para sesiones.

o	Limitar los intentos de inicio de sesión y bloquear temporalmente después de varios intentos fallidos.

**8. Fallas en la Integridad de Software y Datos (Software and Data Integrity Failures)**
    
**•	Descripción:** Vulnerabilidad que permite que el código o los datos sean manipulados, afectando la integridad del sistema.

**•	Métodos de Explotación:**

o	Inyección de código malicioso: Mediante bibliotecas comprometidas, los atacantes pueden introducir malware.

o	Manipulación de la cadena de suministro: Los atacantes alteran software o datos en la cadena de suministro.

**•	Mejores Prácticas de Prevención:**

o	Verificar las firmas de las bibliotecas y componentes utilizados.

o	Utilizar herramientas de análisis de integridad de archivos para detectar cambios no autorizados.

o	Realizar pruebas de integridad en toda la cadena de suministro del software.

**9. Problemas de Registro y Monitoreo (Security Logging and Monitoring Failures)**
    
**•	Descripción:** La falta de un registro y monitoreo adecuados dificulta detectar y responder a incidentes de seguridad.

**•	Métodos de Explotación:**

o	Encubrimiento de ataques: Sin registros o monitoreo adecuados, los ataques pasan desapercibidos.

o	Escalada de incidentes: La ausencia de alertas puede permitir ataques prolongados y dañinos.

**•	Mejores Prácticas de Prevención:**

o	Implementar sistemas de registro para eventos de seguridad críticos.

o	Configurar alertas para detectar comportamientos anómalos.

o	Revisar los registros regularmente y establecer protocolos de respuesta ante incidentes.

**10. Fallas en el Control del Ciclo de Vida de Software (Server-Side Request Forgery - SSRF)**
    
**•	Descripción:** La SSRF permite que los atacantes envíen solicitudes a recursos internos desde el servidor.

**•	Métodos de Explotación:**

o	Manipulación de solicitudes: Los atacantes envían solicitudes a sistemas internos para acceder a datos sensibles.

o	Ataques de red internos: Los atacantes usan SSRF para interactuar con otros recursos internos.

**•	Mejores Prácticas de Prevención:**

o	Limitar el acceso del servidor a recursos internos no necesarios.

o	Validar y restringir todas las solicitudes salientes desde el servidor.

o	Implementar filtros y políticas de control de acceso en el servidor.

### **Conclusión del Taller: Análisis de Vulnerabilidades OWASP Top 10**

Este trabajo resalta la importancia de identificar, comprender y mitigar las principales vulnerabilidades clasificadas en el OWASP Top 10, que representan los riesgos más críticos en la seguridad de aplicaciones modernas. A través del análisis detallado de cada vulnerabilidad, se concluye que:

1. **La seguridad es un proceso continuo**: La prevención de ataques no depende únicamente de soluciones técnicas, sino de un enfoque integral que abarque desde el diseño seguro hasta la monitorización activa.

2. **La educación y la concienciación son fundamentales**: El conocimiento de las vulnerabilidades y sus métodos de explotación permite a los desarrolladores y administradores implementar controles efectivos desde las etapas iniciales del ciclo de vida del software.

3. **La colaboración es clave para la ciberseguridad**: Al trabajar en grupo, cada integrante aporta perspectivas y habilidades únicas, fortaleciendo la comprensión y aplicación de mejores prácticas de seguridad.

4. **La automatización y las herramientas adecuadas mejoran la protección**: Utilizar herramientas como OWASP Dependency-Check, Burp Suite o firewalls de aplicaciones (WAF) ayuda a identificar y mitigar riesgos más rápidamente.

En resumen, este taller demuestra que al adoptar un enfoque preventivo, implementar controles efectivos y mantenerse actualizado frente a nuevas amenazas, es posible minimizar significativamente los riesgos y garantizar la seguridad de las aplicaciones en entornos modernos.
