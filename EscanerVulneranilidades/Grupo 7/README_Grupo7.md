
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
   
![image](https://github.com/user-attachments/assets/95f0cce9-7d60-46ad-8aa4-eafae00afb14)

   ![image](https://github.com/user-attachments/assets/29f1d3b2-760f-4702-a37f-9a7d0cdf47f8)

   ![image](https://github.com/user-attachments/assets/5ad9e15f-46d3-4d57-ae6c-5b9bc36b4dc3)

   ![image](https://github.com/user-attachments/assets/cd829355-0df7-436a-a663-b11e1e8ded39)
   
![image](https://github.com/user-attachments/assets/6b76341e-15df-4465-8405-9360628b391d)

![image](https://github.com/user-attachments/assets/6a688cd8-e914-4430-bcd6-8a9cc82022e4)

![image](https://github.com/user-attachments/assets/6bcf4f3a-b0e9-495a-a728-14f5b7267c84)
![image](https://github.com/user-attachments/assets/cf74cd4f-295c-43c9-a183-56ec74b82c16)

![image](https://github.com/user-attachments/assets/46e8f399-02b4-4d46-afc9-a04052fb2053)

![image](https://github.com/user-attachments/assets/80ec6797-940a-4141-b9ec-ba1d3d5ffc87)



![image](https://github.com/user-attachments/assets/fc8a7b69-c6d8-435f-acc3-39aa789e6cd6)


![image](https://github.com/user-attachments/assets/0136bc33-92c7-4503-a2ec-30762c3c944f)


