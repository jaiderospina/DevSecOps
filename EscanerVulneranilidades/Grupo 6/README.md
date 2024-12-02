# Escaneo de Vulnerabilidades con OpenVAS - Grupo 6

## Integrantes
1. Erick Celis
2. Diego Sindicue
3. Integrante 3

## Introducción

Este proyecto consiste en la utilización de la herramienta OpenVAS (Open Vulnerability Assessment System) para analizar vulnerabilidades en una aplicación web vulnerable (`DVWA - Damn Vulnerable Web Application`). Como parte del trabajo, se documentaron los pasos de instalación, configuración y análisis, además de subir la imagen personalizada a DockerHub.

El propósito principal de esta actividad es aprender a identificar vulnerabilidades en entornos controlados y documentar el proceso como referencia para futuras auditorías de seguridad.

## Paso 1: Instalación y Configuración de OpenVAS

1. **Actualizar el sistema operativo:**
   Actualizamos los paquetes del sistema para asegurarnos de contar con las últimas versiones.
   ```bash
   sudo apt-get update && sudo apt-get upgrade -y
   ```
2. **Instalar OpenVAS: Instalamos OpenVAS, que forma parte de gvm**
   ```bash
   sudo apt-get install -y gvm```
3. **Configurar OpenVAS: Configuramos todos los componentes necesarios, como la base de datos de vulnerabilidades y las dependencias.**
   ```bash
   sudo gvm-setup
   ```
4. **Verificar la configuración:**
   Actualizamos los paquetes del sistema para asegurarnos de contar con las últimas versiones.
   ```bash
   sudo gvm-check-setup
   ```
5. **Iniciar los servicios:**
   Ejecutamos OpenVAS y accedemos a la interfaz gráfica desde un navegador.
   ```bash
   sudo gvm-start
   ```
   
  * URL de acceso: https://localhost:9392
  * Usuario y contraseña: Generados durante la configuración.

## Paso 2: Configuración del Contenedor Vulnerable

1. **Instalar Docker:**  
   Instalamos Docker para gestionar los contenedores.  
   ```bash
   sudo apt-get install -y docker.io
   ```
2. **Descargar el Contenedor Vulnerable (DVWA):**  
   Utilizamos Docker para descargar la imagen de DVWA desde DockerHub.
   ```bash
   sudo docker pull vulnerables/web-dvwa
   ```
3. **Ejecutar el Contenedor:**  
   Iniciamos el contenedor en el puerto 8080 para que esté accesible desde el navegador o herramientas de escaneo.
   ```bash
   sudo docker run -d --name dvwa -p 8080:80 vulnerables/web-dvwa
   ```
4. **Verificar el Contenedor en Ejecución:**  
   Iniciamos el contenedor en el puerto 8080 para que esté accesible desde el navegador o herramientas de escaneo.
   ```bash
   sudo docker ps
   ```
5. **Obtener la Dirección IP del Contenedor**  
   Si necesitas la dirección IP específica del contenedor para enlazarlo con greenbone con este comando puedes sacarla
   ```bash
   sudo docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' dvwa
   ```
## Paso 3: Crear un Objetivo y una Tarea de Escaneo en OpenVAS

1. **Acceder a la Interfaz Web de OpenVAS:**  
   Abrimos un navegador y accedemos a la interfaz gráfica de OpenVAS.  
   - URL: `https://localhost:9392`  
   - Inicia sesión con las credenciales generadas durante la configuración.

2. **Crear un Objetivo:**  
   Configuramos un nuevo objetivo para el análisis de vulnerabilidades.  
   - Navegamos a `Configuration > Targets`.  
   - Hacemos clic en `New Target`.  
   - Completamos los campos requeridos:
     - **Name:** `DVWA Target`.
     - **Hosts:** Ingresamos la dirección IP del contenedor (`127.0.0.1` o la dirección obtenida con `docker inspect`).
     - **Port List:** Seleccionamos `All IANA Assigned TCP`.  
   - Guardamos el objetivo.

3. **Crear una Tarea de Escaneo:**  
   Asociamos el objetivo creado a una nueva tarea de escaneo.  
   - Navegamos a `Scans > Tasks`.  
   - Hacemos clic en `New Task`.  
   - Configuramos los siguientes campos:
     - **Name:** `DVWA Scan`.
     - **Target:** Seleccionamos `DVWA Target`.
     - **Scanner:** Dejamos seleccionado `OpenVAS Default`.  
   - Guardamos la tarea.

4. **Iniciar el Escaneo:**  
   Ejecutamos la tarea para iniciar el escaneo.  
   - En la lista de tareas (`Scans > Tasks`), localizamos `DVWA Scan`.
   - Hacemos clic en el botón `Play` (▶️) para iniciar el escaneo.  

5. **Monitorear el Progreso:**  
   Verificamos el estado del escaneo en la columna `Status`.  
   - Los posibles estados son:
     - `Requested`: El escaneo ha sido solicitado.
     - `Running`: El escaneo está en progreso.
     - `Done`: El escaneo ha finalizado.

6. **Revisar los Resultados del Escaneo:**  
   - Una vez completado el escaneo, vamos a `Scans > Reports`.  
   - Seleccionamos el informe asociado a `DVWA Scan`.  
   - Descargamos el informe en formato PDF, HTML o XML para análisis posterior.

## Paso 4: Subir la Imagen Escaneada a DockerHub

1. **Verificar que el Contenedor está en Ejecución:**  
   Antes de subir la imagen, confirmamos que el contenedor vulnerable está corriendo correctamente.  
   ```bash
   sudo docker ps
   ```
2. **Crear una Nueva Imagen Basada en el Contenedor Escaneado:**  
   Creamos una nueva imagen del contenedor dvwa escaneado y le asignamos un nombre descriptivo. 
   ```bash
   sudo docker commit dvwa grupo6/dvwa_vulnerable
   ```
3. **Etiquetar la Imagen para DockerHub:**  
   Asignamos una etiqueta a la imagen para que coincida con el repositorio de DockerHub. Asegurense de usar su nombre de usuario en dockerhub.
   ```bash
   sudo docker tag grupo6/dvwa_vulnerable erickc09/dvwa_vulnerable:v1
   ```
4. **Iniciar Sesión en DockerHub:**  
   Nos autenticamos en DockerHub con nuestras credenciales.
   ```bash
   sudo docker login
   ```
5. **Subir la Imagen a DockerHub:**  
   Subimos la imagen etiquetada a nuestro repositorio en DockerHub.
   ```bash
   sudo docker push erickc09/dvwa_vulnerable:v1
   ```
   















