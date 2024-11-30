
# **Reporte: Taller de Contenerización y Escaneo de Vulnerabilidades con OpenVAS**

## **Integrantes del Grupo 7**

| Nombre      | Apellido     |
|-------------|--------------|
| Michelle    | Gutierrez    |
| Harold      | Ramirez      |
| Camilo      | Porras       |

## Descripción
```mermaid
graph TD;
    A-->Confguracion_Debian-Greenbone;
    A-->B;
    B-->Configuracion_ip-actualizaciones;
    B-->descarga_de_imagen_vulnerable;
    B-->C;
    C-->creacion_de_tarea-resultados;
    C-->upload_dockerhub_image_scanning;
```

## **Objetivo del Taller**

El objetivo del taller fue crear y configurar un contenedor Docker con OpenVAS, realizar un escaneo de vulnerabilidades en un sistema vulnerable, y documentar todo el proceso, incluyendo la creación, actualización y análisis de vulnerabilidades. Este ejercicio también incluye la configuración de un contenedor vulnerable, el escaneo de red, y la creación de tareas programadas dentro del contenedor de OpenVAS.

---

## **Proceso de Creación del Contenedor con OpenVAS**

### **Paso 1: Creación de la Máquina Virtual Ubuntu**

Se comenzó con la creación de una máquina virtual Ubuntu, que serviría como base para la instalación de Docker y otros componentes necesarios para el taller.

1. **Instalación de Ubuntu**:
   - Se descargó la imagen ISO de Ubuntu desde su sitio oficial.
   - **Captura de pantalla**: Se muestra la máquina virtual recién creada con Ubuntu.

   ![Paso 1](https://github.com/user-attachments/assets/a8a1c242-37be-497b-be45-1ea4066de983)

### **Paso 2: Instalación de Docker en Ubuntu**

Para la instalación de Docker en Ubuntu, se siguieron los siguientes pasos:

1. **Instalación de Docker**:
   - Ejecutamos los siguientes comandos para instalar Docker:
     ```bash
     sudo apt-get update
     sudo apt-get install -y docker.io
     ```
   - Verificamos la instalación con:
     ```bash
     docker --version
     ```

   ![Paso 2](https://github.com/user-attachments/assets/46bc36af-f9a9-4527-b646-83050e8905d5)

### **Paso 3: Descargar la Imagen de OpenVAS**

Usamos el comando Docker para descargar la imagen de OpenVAS (Greenbone Vulnerability Management).

1. **Comando para descargar la imagen**:
   ```bash
   docker pull greenbone/gvm
   ```

   ![Paso 3](https://github.com/user-attachments/assets/c81b24de-f0b9-4ace-aa20-e83168aca3b7)

### **Paso 4: Crear el Contenedor Docker con OpenVAS**

Después de descargar la imagen de OpenVAS, creamos el contenedor asignándole una IP válida dentro del segmento local y configurando el puerto para acceder a la interfaz web de OpenVAS.

1. **Comando para crear el contenedor**:
   ```bash
   docker run -d --name openvas -e PASSWORD=admin -p 443:443 greenbone/gvm
   ```

   ![Paso 4](https://github.com/user-attachments/assets/a003bbda-4714-4343-b82b-e326d9972432)

---

## **Configuración y Ejecución de un Repositorio Vulnerable**

### **Paso 5: Descargar un Repositorio Vulnerable**

Para realizar pruebas de escaneo, se descargó un repositorio vulnerable, como el proyecto DVWA (Damn Vulnerable Web Application), que se ejecutaría en un contenedor Docker.

1. **Captura de pantalla de la descarga del repositorio vulnerable**:

   ![Descarga de máquina vulnerable](https://github.com/user-attachments/assets/de3eeddb-3fa2-4343-8d2d-f964dd412a06)

### **Paso 6: Ejecutar el Repositorio Vulnerable**

1. **Ejecutar el contenedor con el repositorio vulnerable**:
   ```bash
   docker run -d --name vulnerable-repo --network host vulnerable/repo
   ```

   ![Correr el repo vulnerable](https://github.com/user-attachments/assets/50c4e98a-781a-4a9a-8935-6450d18a5cfc)

### **Paso 7: Acceder al Contenedor Vulnerable**

Una vez el contenedor vulnerable estaba en ejecución, accedimos al repositorio desde un navegador para verificar que estuviera disponible y listo para ser escaneado.

1. **Acceso al contenedor vulnerable**:
   - Abrimos el navegador e ingresamos la IP del contenedor vulnerable.
   - **Capturas de pantalla de la interfaz del repositorio vulnerable**:

   ![Abrir repo vulnerable](https://github.com/user-attachments/assets/0908e6d1-6820-4d30-b24b-ee770164869a)


---

## **Escaneo de Vulnerabilidades con OpenVAS**

### **Paso 8: Configuración de OpenVAS**

1. **Acceder a la interfaz web de OpenVAS**:
   - Accedimos a la interfaz de OpenVAS a través del navegador, usando la dirección `https://<ip_del_contenedor>:443`.
   - Configuramos el escaneo especificando los parámetros necesarios y seleccionamos el perfil de escaneo más adecuado.
  
   ![image](https://github.com/user-attachments/assets/95f0cce9-7d60-46ad-8aa4-eafae00afb14)

   ![image](https://github.com/user-attachments/assets/29f1d3b2-760f-4702-a37f-9a7d0cdf47f8)

   

### **Paso 9: Realizar el Escaneo de Vulnerabilidades**

1. **Iniciar el escaneo**:
   - Iniciamos el escaneo del contenedor vulnerable utilizando la interfaz web de OpenVAS.
   - **Captura de pantalla de los resultados del escaneo**:

   ![Greenbone](https://github.com/user-attachments/assets/829ba0df-6e51-444f-b873-a84a8fcb6e2b)

   ![Segundo análisis](https://github.com/user-attachments/assets/7da7efe5-ef62-4faf-b43d-833c83ac3ac5)


---

### **Paso 10: Analisis de vulneravilidades**

1. **Subir la imagen de OpenVAS a DockerHub**:
   - Podemos observar 5 vulneravulidades, una alta, 2 medias y 2 bajas

   ![image](https://github.com/user-attachments/assets/20d5e7d7-f1bc-445a-af8b-24cae4f1240d)

   - Si ampliamos la informacion podemos ver el detalle de la vulnerabilidad.
  
   ![image](https://github.com/user-attachments/assets/eb854839-9625-456d-a342-0462e17c76e8)

   ![image](https://github.com/user-attachments/assets/6b91eae0-3cee-492b-abec-92024f274c59)

   - Adicional podemos observar con detalle los CVE del escaneo realizado
  
   ![image](https://github.com/user-attachments/assets/8e5eed5e-6b0e-4de0-895d-820138b42b9c)


## **Conclusión**

Este taller permitió la creación y configuración de un contenedor Docker con OpenVAS, así como la realización de un escaneo de vulnerabilidades sobre un sistema vulnerable. Se cubrieron todos los pasos necesarios, desde la creación de la máquina virtual hasta la subida de la imagen a DockerHub, asegurando que el proceso estuviera bien documentado y que los resultados del escaneo fueran correctamente registrados. 

Este ejercicio no solo facilita el entendimiento del uso de OpenVAS en contenedores Docker, sino también el análisis y gestión de vulnerabilidades en entornos controlados.
