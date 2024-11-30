
## **Integrantes del Grupo 7**

| Nombre      | Apellido     |
|-------------|--------------|
| Michelle    | Gutierrez    |
| Harold      | Ramirez      |
| Camilo      | Porras       |

---

## **Objetivo del Taller**

Crear y configurar un contenedor Docker con OpenVAS, realizar un escaneo de vulnerabilidades a un sistema vulnerable, y documentar todo el proceso, incluyendo la creación, actualización y análisis de vulnerabilidades.

---

## **Creación del Contenedor Ubuntu con OpenVAS**

### **Paso 1: Crear una Máquina Virtual Ubuntu**

1. Utiliza una máquina virtual con Ubuntu para la instalación inicial de Docker y otras dependencias.
   - **Imagen inicial**: Descargar la ISO de Ubuntu desde el sitio oficial.
   - **Captura de pantalla**: Muestra la imagen de la máquina virtual recién creada.

   ![Paso 1](https://github.com/user-attachments/assets/a8a1c242-37be-497b-be45-1ea4066de983)

### **Paso 2: Instalación de Docker en Ubuntu**

1. Instalar Docker siguiendo los pasos estándar para Ubuntu:
   ```bash
   sudo apt-get update
   sudo apt-get install -y docker.io
   ```
   - Verificar la instalación:
   ```bash
   docker --version
   ```

   ![Paso 2](https://github.com/user-attachments/assets/46bc36af-f9a9-4527-b646-83050e8905d5)

### **Paso 3: Descargar la Imagen Docker de OpenVAS**

1. Utiliza el comando para descargar la imagen de OpenVAS:
   ```bash
   docker pull greenbone/gvm
   ```

   ![Paso 3](https://github.com/user-attachments/assets/c81b24de-f0b9-4ace-aa20-e83168aca3b7)

### **Paso 4: Crear el Contenedor Docker con OpenVAS**

1. Una vez descargada la imagen, crea el contenedor y asígnale una IP válida dentro del segmento local.
   ```bash
   docker run -d --name openvas -e PASSWORD=admin -p 443:443 greenbone/gvm
   ```

   ![Paso 4](https://github.com/user-attachments/assets/a003bbda-4714-4343-b82b-e326d9972432)

---

## **Descarga y Configuración de un Repositorio Vulnerable**

### **Paso 5: Descargar el Repositorio Vulnerable**

1. Para pruebas de escaneo, descarga un repositorio vulnerable (por ejemplo, un contenedor vulnerable como DVWA).
   - **Captura de pantalla**: Imagen de la descarga del repositorio.

   ![Descarga de máquina vulnerable](https://github.com/user-attachments/assets/de3eeddb-3fa2-4343-8d2d-f964dd412a06)

### **Paso 6: Ejecutar el Repositorio Vulnerable**

1. Inicia el contenedor con el repositorio vulnerable descargado:
   ```bash
   docker run -d --name vulnerable-repo --network host vulnerable/repo
   ```

   ![Correr el repo vulnerable](https://github.com/user-attachments/assets/50c4e98a-781a-4a9a-8935-6450d18a5cfc)

### **Paso 7: Acceder al Contenedor Vulnerable**

1. Accede al repositorio vulnerable a través del navegador y verifica las vulnerabilidades.
   - **Captura de pantalla**: Mostrar cómo se accede al contenedor vulnerable desde el navegador.

   ![Abrir repo vulnerable](https://github.com/user-attachments/assets/0908e6d1-6820-4d30-b24b-ee770164869a)

---

## **Configuración y Ejecución del Escaneo de Vulnerabilidades con OpenVAS**

### **Paso 8: Configuración de OpenVAS**

1. Inicia sesión en el panel web de OpenVAS (generalmente en `https://<ip_del_contenedor>:443`).
   - Configura los parámetros del escaneo, selecciona las opciones de escaneo de vulnerabilidades y ajusta los perfiles según sea necesario.

   ![Greenbone](https://github.com/user-attachments/assets/829ba0df-6e51-444f-b873-a84a8fcb6e2b)

### **Paso 9: Realización del Escaneo**

1. Realiza el escaneo contra el contenedor vulnerable utilizando OpenVAS.
   - Documenta el proceso del escaneo y toma capturas de pantalla de los resultados del análisis de vulnerabilidades.
   - Ejemplo de comando para iniciar un escaneo:
     ```bash
     gvm-cli ssh --hostname <ip_openvas> --username admin --password admin --scan <nombre_del_scan>
     ```

   ![Segundo análisis](https://github.com/user-attachments/assets/7da7efe5-ef62-4faf-b43d-833c83ac3ac5)

---

## **Subir la Imagen a DockerHub y Documentación Final**

### **Paso 10: Crear y Subir la Imagen Docker a DockerHub**

1. Una vez configurado y probado el contenedor con OpenVAS, crea la imagen Docker:
   ```bash
   docker commit openvas nombre_usuario/openvas
   docker push nombre_usuario/openvas
   ```

   - Documenta el proceso de creación de la imagen y su subida a DockerHub.
   - **Captura de pantalla**: Mostrar cómo se realiza el push de la imagen.

   ![Imagen subida a DockerHub](https://github.com/user-attachments/assets/c9ab83c7-c55e-4bcc-ae3c-0db1f9cec7b7)

---

### **Conclusión**

Este taller ha demostrado cómo contenerizar OpenVAS, realizar escaneos de vulnerabilidades en un sistema vulnerable, y documentar todo el proceso paso a paso, incluyendo la creación, configuración y análisis. Además, se ha cubierto el proceso de subir la imagen Docker a DockerHub para su reutilización.

---

Esta versión documenta con más detalle cada paso del proceso, asegurando que se sigan las mejores prácticas y que toda la información esté organizada de forma clara y fácil de seguir.




