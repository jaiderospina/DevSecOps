La **contenerización** es una tecnología que permite empaquetar una aplicación junto con todas sus dependencias (como bibliotecas, configuraciones y archivos necesarios) en una unidad estandarizada llamada **contenedor**. Este contenedor es una entidad aislada que se ejecuta sobre el sistema operativo del host, proporcionando un entorno consistente para la aplicación, independientemente de dónde se despliegue.

**Principales características de la contenerización:**

1. **Aislamiento de entornos**: Cada contenedor opera de forma independiente y aislada de otros contenedores y del sistema operativo host. Esto significa que los procesos dentro de un contenedor no interfieren con los de otro.

2. **Portabilidad**: Los contenedores pueden ejecutarse en cualquier sistema que tenga un motor de contenedores compatible (como Docker Engine), lo que facilita mover aplicaciones entre entornos de desarrollo, pruebas y producción sin cambios en el código.

3. **Ligereza y eficiencia**: A diferencia de las máquinas virtuales, los contenedores comparten el núcleo del sistema operativo del host, lo que reduce el consumo de recursos y permite ejecutar múltiples contenedores en un solo servidor de manera eficiente.

4. **Escalabilidad**: Es sencillo escalar aplicaciones basadas en contenedores, ya que se pueden replicar y administrar fácilmente múltiples instancias para manejar cargas de trabajo variables.

**Beneficios de la contenerización:**

- **Consistencia en el despliegue**: Al empaquetar todas las dependencias, se asegura que la aplicación se comporte de la misma manera en diferentes entornos, eliminando el clásico problema de "funciona en mi máquina".

- **Rapidez en el inicio y despliegue**: Los contenedores se inician en segundos, lo que acelera el ciclo de desarrollo y despliegue de aplicaciones.

- **Mejor utilización de recursos**: Al ser más ligeros que las máquinas virtuales, permiten una mayor densidad de aplicaciones en el mismo hardware.

- **Facilidad de integración y entrega continua (CI/CD)**: Los contenedores se integran bien con herramientas de automatización, facilitando prácticas de DevOps.

**Herramientas y tecnologías relacionadas:**

- **Docker**: Es la plataforma más popular para crear, desplegar y ejecutar contenedores. Proporciona un conjunto de herramientas y comandos para trabajar con contenedores de manera sencilla.

- **Kubernetes**: Es un sistema de orquestación de contenedores que automatiza el despliegue, escalado y gestión de aplicaciones en contenedores en un clúster de servidores.

- **Docker Compose**: Permite definir y ejecutar aplicaciones de Docker con múltiples contenedores utilizando un archivo YAML para configurar los servicios.

**Ejemplo práctico:**

Imagina que desarrollas una aplicación web que requiere una versión específica de Node.js y ciertas dependencias. Sin contenerización, tendrías que configurar cada servidor donde despliegues la aplicación para que tenga exactamente las mismas versiones y configuraciones, lo cual es propenso a errores y consume tiempo.

Con contenerización:

1. **Creas una imagen de Docker** que incluye tu aplicación y todas sus dependencias.

2. **Empaquetas todo en un contenedor**, asegurando que siempre se ejecute en el entorno correcto.

3. **Despliegas el contenedor** en cualquier servidor que tenga Docker instalado, sin preocuparte por las configuraciones subyacentes.

Esto garantiza que tu aplicación funcionará de manera consistente en cualquier entorno, simplificando el proceso de despliegue y reduciendo problemas relacionados con configuraciones inconsistentes.

## VARIOS-TIPS

- **Ver IP de un conenedor especifico**
- docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' NOMBRE CONTAINER
-  

# Referencias.

- https://github.com/jaiderospina/Docker20242

