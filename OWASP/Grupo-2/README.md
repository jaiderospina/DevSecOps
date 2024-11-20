Grupo 2 Integrantes.

Adriana Tobon 


VULNERABILIDAD, MÉTODOS DE EXPLOTACIÓN Y RECOMENDACIONES PRÁCTICAS DEL OWASP TOP 10.

(Open Worldwide Application Security Project)
Es una comunidad abierta dedicada a facilitar a las organizaciones el diseño, desarrollo, adquisición, operación y mantenimiento de software para aplicaciones seguras en las que se pueda confiar.

1.	Pérdida de control de acceso: 

Se produce cuando la aplicación permite que los atacantes puedan acceder a funciones o datos no autorizados. Esto puede deberse a referencias directas inseguras, que pueden surgir cuando una aplicación no puede validar o autorizar la entrada del usuario.

 Métodos de Explotación:

•	Referencias directas inseguras (por ejemplo, acceder a recursos mediante URL manipuladas).
•	Escalación de privilegios aprovechando fallos en la autorización.

Recomendaciones:

•	Implementar controles de acceso basados en roles (RBAC).
•	Validar siempre la autorización del usuario antes de acceder a recursos.
•	Realizar auditorías de acceso y permisos.

2.	Fallas criptográficas: 

Pueden dar lugar a infracciones de datos, acceso no autorizado a información confidencial y el incumplimiento de las normas de privacidad de datos, como el Reglamento General de Protección de Datos de la UE (RGPD) y estándares financieros como las Normas de Seguridad de Datos PCI (PCI DSS). Estos fallos pueden deberse a un almacenamiento criptográfico no seguro, al almacenamiento de datos en texto sin formato o a una gestión de claves no segura.

Métodos de Explotación:

•	Un atacante puede manipular parámetros de URL o formularios para acceder a recursos a los que no debería tener acceso. Por ejemplo, cambiar un identificador en una URL para acceder a los datos de otro usuario.
•	Utilizar credenciales comprometidas o manipuladas para ingresar a áreas protegidas de la aplicación.

 Recomendaciones Prácticas:

•	Asegurarse de que todos los recursos y funcionalidades de la aplicación estén protegidos mediante controles de acceso adecuados.
•	La aplicación debe validar las solicitudes y asegurarse de que el usuario tenga los permisos necesarios antes de acceder a datos o funciones.

3.	Ataques de inyección:

Los fallos de inyección ocurren cuando los atacantes introducen datos maliciosos en lenguajes de consulta o comandos debido a la falta de validación, filtrado o saneamiento de los datos por parte de la aplicación. Estos ataques incluyen inyección de NoSQL, comandos del sistema operativo, LDAP y SQL, así como Cross-site scripting (XSS), donde los atacantes inyectan scripts maliciosos en páginas web. Las consecuencias pueden incluir el robo de información confidencial, como credenciales de inicio de sesión, datos personales o cookies de sesión.

Métodos de Explotación:

•	Acceso a datos sensibles almacenados en texto plano.
•	Uso de algoritmos de cifrado débiles o desactualizados.

Recomendaciones:

•	Usar cifrados fuertes y estándares actualizados (AES, RSA).
•	No almacenar datos sensibles en texto plano y gestionar adecuadamente las claves.
•	Implementar prácticas de seguridad en el manejo de datos, cumpliendo con normativas como GDPR y PCI DSS.

4.	Diseño inseguro:

Estos fallos pueden ocurrir si una aplicación se ha diseñado para depender de procesos poco seguros de por sí, o cuando no se implementan los controles de seguridad necesarios para defenderse frente a ataques específicos.

Métodos de Explotación:

•	Inyección SQL, NoSQL, comandos del sistema operativo, LDAP, y XSS.

Recomendaciones:

•	Utilizar consultas parametrizadas y ORM.
•	Escapar todas las entradas del usuario y validar su contenido.
•	Implementar Content Security Policy (CSP) para mitigar XSS.

5.	Configuración de Seguridad incorrecta:

 Los riesgos debidos a configuraciones de seguridad erróneas también pueden deberse a permisos configurados incorrectamente en los servicios en la nube, o a la instalación o habilitación de funciones innecesarias, como puertos, servicios, cuentas o privilegios no utilizados. La configuración errónea tanto de las aplicaciones web como de las API es un riesgo importante, ya que los principales proveedores de nube tienen distintas posiciones de seguridad de forma predeterminada y la arquitectura está cada vez más descentralizada y distribuida en una estructura multinube.

Métodos de Explotación:

•	Aprovechar la falta de controles de seguridad desde la fase de diseño.

Recomendaciones:

•	Incorporar revisiones de seguridad en el ciclo de vida del desarrollo de software.
•	Educar a los desarrolladores sobre las mejores prácticas de seguridad.

6.	Componentes vulnerables y desactualizados:

Estos riesgos pueden estar causados por software no compatible o no actualizado, como el del sistema operativo (SO), el servidor web o de aplicaciones, el sistema de gestión de bases de datos (DBMS), las aplicaciones, las API y todos los componentes, entornos de ejecución y bibliotecas. Estas amenazas son especialmente peligrosas cuando las organizaciones no cuentan con medidas oportunas basadas en los riesgos para corregir o actualizar la Plataforma.

Métodos de Explotación:

•	Explotar configuraciones predeterminadas inseguras o servicios innecesarios habilitados.

Recomendaciones:

•	Realizar auditorías de seguridad para asegurar configuraciones apropiadas.
•	Desactivar funciones y servicios que no sean necesarios.
•	Mantener una política de gestión de configuración.

7.	Fallas de identificación y autenticación.

Los fallos en estas áreas pueden permitir ataques automatizados como el relleno de credenciales o credential stuffing. Las vulnerabilidades relacionadas con contraseñas son la fuente más común de estos riesgos, ya que muchas personas reutilizan las contraseñas o usan contraseñas predeterminadas, débiles o conocidas. Los problemas de gestión de sesiones también pueden provocar ataques relacionados con la autenticación, sobre todo si las sesiones de usuario o los tokens de autenticación no se invalidan correctamente durante el cierre de sesión o un período de inactividad. 

Métodos de Explotación:

•	Explotar vulnerabilidades conocidas en bibliotecas y componentes de software.

Recomendaciones:

•	Mantener todos los componentes actualizados y realizar auditorías de dependencias.
•	Utilizar herramientas automatizadas para detectar vulnerabilidades en el software.
•	Implementar una política de gestión de parches regular.

8.	Fallas en el software y en la integridad de los datos:

 Esto puede ocurrir cuando una aplicación se basa en complementos, bibliotecas o módulos de fuentes, repositorios y CDN que no son de confianza. También puede ocurrir durante las actualizaciones de software, modificaciones de datos confidenciales y cambios en las canalizaciones CI/CD que no se validan. Es posible que los atacantes puedan cargar sus propias actualizaciones para distribuirlas y ejecutarlas en todas las instalaciones. 

Métodos de Explotación:

•	Ataques de relleno de credenciales (credential stuffing) y ataques de fuerza bruta.

Recomendaciones:

•	Implementar autenticación multifactor (MFA).
•	Forzar políticas de contraseñas seguras (longitud, complejidad, expiración).
•	Invalidar sesiones de usuario al cerrar sesión o después de períodos de inactividad.

9.	Fallas en el registro y monitoreo de la seguridad:

Un acceso y supervisión inadecuados pueden obstaculizar la detección y la respuesta a tiempo a los incidentes de seguridad, lo que dificulta la identificación y la mitigación de ataques o actividades no autorizadas. 

Métodos de Explotación:

•	Cargar actualizaciones maliciosas en componentes no verificados.

Recomendaciones:

•	Validar la integridad de las actualizaciones y usar firmas digitales.
•	Implementar controles de acceso y monitoreo en las canalizaciones CI/CD.
•	Utilizar bibliotecas y componentes de fuentes confiables.

10.	Server-side request forgery (SSRF)- Falsificación de solicitud del lado del servidor 

Estas vulnerabilidades se producen cuando una aplicación no valida ni sanea una dirección URL introducida por un usuario antes de extraer datos de un recurso remoto. Los atacantes pueden usar estos fallos para forzar a las aplicaciones a que accedan a destinos web maliciosos, incluso aunque estén protegidas por un cortafuegos u otro tipo de defensa.

Métodos de Explotación:

•	Actividades maliciosas que no son detectadas debido a la falta de monitoreo.

Recomendaciones:

•	Implementar un registro adecuado de eventos de seguridad y monitoreo continuo.
•	Utilizar herramientas de detección de intrusiones y gestión de información y eventos de seguridad.
•	Realizar revisiones periódicas y auditorías de seguridad.
