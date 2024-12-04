#Integrantes: 
- Erik Celis
- Diego Padilla
- Diego Sindicue

# **Informe Técnico: Configuración de un Entorno DevSecOps**

## **Introducción**

El propósito de este informe es documentar el proceso de configuración de un entorno **DevSecOps** que integra controles de seguridad en un pipeline CI/CD. Este entorno utiliza herramientas como **Node.js**, **Docker**, y **Git**, entre otras, para implementar las mejores prácticas en desarrollo seguro. Los pasos iniciales incluyen la creación de un entorno de trabajo, la instalación de dependencias necesarias y la configuración básica de las herramientas.



## **1. Creación del Entorno de Trabajo**

### **1.1 Crear el Directorio del Proyecto**

Se inicia creando un directorio llamado `devsecops-env`, que será la base del proyecto. Luego se accede a dicho directorio.

**Comando utilizado:**

```bash
mkdir devsecops-env
cd devsecops-env
```

**Resultado visible en terminal:**

![Creación del Directorio](./images/creacion-directorio.png)



## **2. Instalación de Node.js**

### **2.1 Configuración Inicial de Node.js**

Para configurar Node.js, se utiliza el script oficial de NodeSource. Este paso asegura que las fuentes necesarias estén disponibles para la instalación.

**Comando utilizado:**

```bash
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```

**Resultado visible en terminal:**

![Advertencia de Node.js](./images/deprecation-nodejs.png)

_Nota: Aunque aparece una advertencia indicando que la versión 16.x.x ya no es soportada activamente, se procede con el proceso para fines de compatibilidad en el proyecto._



### **2.2 Instalación de Node.js**

Una vez configurado NodeSource, se instala Node.js utilizando el gestor de paquetes `apt`. Este paso también instala todas las dependencias necesarias.

**Comando utilizado:**

```bash
sudo apt install -y nodejs
```

**Resultado visible en terminal:**

![Instalación de Node.js](./images/instalacion-nodejs.png)



### **2.3 Verificar la Instalación**

Después de la instalación, es importante confirmar que Node.js está funcionando correctamente. Esto se hace verificando la versión instalada con el comando `node -v`.

**Comando utilizado:**

```bash
node -v
```

**Resultado visible en terminal:**

![Verificación de Node.js](./images/verificacion-nodejs.png)



## **3. Configuración del Proyecto Node.js**

### **3.1 Inicialización del Proyecto con npm**

Se inicializa el proyecto Node.js utilizando `npm init -y`, lo que genera automáticamente el archivo `package.json` con una configuración predeterminada.

**Comando utilizado:**

```bash
npm init -y
```

**Resultado visible en terminal:**

![Inicialización de npm](./images/npm-init.png)



### **3.2 Creación de la Estructura del Proyecto**

Se crean las carpetas necesarias para organizar el código y los archivos iniciales del proyecto. Las carpetas incluyen `src/controllers` y `src/models`, mientras que los archivos como `index.js`, `documentsController.js`, y `documents.js` se generan dentro de su respectiva estructura.

**Comando utilizado:**

```bash
mkdir src src/controllers src/models
touch src/index.js src/controllers/documentsController.js src/models/documents.js
touch Dockerfile docker-compose.yml
```

**Resultado visible en terminal:**

![Estructura del proyecto](./images/estructura-proyecto.png)



### **3.3 Instalación de Express**

Para configurar un servidor en Node.js, se instala el paquete **Express**, que simplifica el desarrollo de aplicaciones web.

**Comando utilizado:**

```bash
npm install express
```

**Resultado visible en terminal:**

![Instalación de Express](./images/install-express.png)



### **3.4 Instalación de Nodemon (Desarrollo)**

Se instala **Nodemon** como dependencia de desarrollo. Esta herramienta permite reiniciar automáticamente el servidor cada vez que se detectan cambios en los archivos, mejorando la productividad durante el desarrollo.

**Comando utilizado:**

```bash
npm install --save-dev nodemon
```

**Resultado visible en terminal:**

![Instalación de Nodemon](./images/install-nodemon.png)



## **4. Desarrollo del Proyecto**

### **4.1 Crear el archivo `index.js`**

Se crea el archivo principal `index.js` en la carpeta `src`. Este archivo contiene la configuración del servidor utilizando **Express**. Incluye las rutas principales, middleware para parsear JSON y la importación del controlador de documentos.

**Comando utilizado para abrir el archivo:**

```bash
nano src/index.js
```

**Contenido del archivo `index.js`:**

```javascript
// Importar módulos y configuraciones
const express = require('express');
const bodyParser = require('body-parser');
const app = express();
const port = 3000;

// Middleware para parsear JSON
app.use(bodyParser.json());

// Importar rutas
const documentsController = require('./controllers/documentsController');
app.use('/documents', documentsController);

// Ruta principal
app.get('/', (req, res) => {
    res.send('Bienvenido al sistema de gestión de documentos');
});

// Iniciar el servidor
app.listen(port, () => {
    console.log(`Servidor en ejecución en http://localhost:${port}`);
});
```

**Resultado visible en terminal:**

![Contenido del archivo index.js](./images/index-js.png)


### **4.2 Crear el modelo `documents.js`**

Se define el archivo `documents.js` en la carpeta `src/models`. Este archivo contiene las funciones para crear, editar y gestionar documentos simulados.

**Comando utilizado para abrir el archivo:**

```bash
nano src/models/documents.js
```

**Contenido del archivo `documents.js`:**

```javascript
function editDocument(id, newData) {
    const document = documents.find(doc => doc.id === id);
    if (!document) {
        throw new Error('Documento no encontrado');
    }
    Object.assign(document, newData);
    return document;
}

// Exportar las funciones del modelo
module.exports = { createDocument, editDocument, documents };
```

**Resultado visible en terminal:**

![Contenido del archivo documents.js](./images/documents-js.png)



## **5. Creación de Controladores y Configuración de Docker**

### **5.1 Crear el archivo `documentsController.js`**

Se define el controlador `documentsController.js` en la carpeta `src/controllers`. Este archivo gestiona las rutas de la API, permitiendo crear, editar, listar y gestionar documentos.

**Comando utilizado para abrir el archivo:**

```bash
nano src/controllers/documentsController.js
```

**Contenido del archivo `documentsController.js`:**

```javascript
const express = require('express');
const router = express.Router();
const { createDocument, editDocument, documents } = require('../models/documents');

// Ruta para crear un nuevo documento
router.post('/', (req, res) => {
    try {
        const data = req.body;
        const newDocument = createDocument(data);
        res.status(201).json(newDocument);
    } catch (error) {
        res.status(500).json({ error: error.message });
    }
});

// Ruta para editar un documento existente
router.put('/:id', (req, res) => {
    try {
        const id = parseInt(req.params.id, 10);
        const newData = req.body;
        const updatedDocument = editDocument(id, newData);
        res.json(updatedDocument);
    } catch (error) {
        res.status(500).json({ error: error.message });
    }
});

// Ruta para listar todos los documentos
router.get('/', (req, res) => {
    res.json(documents);
});

// Exportar el router
module.exports = router;
```
```

**Resultado visible en terminal:**

![Contenido del archivo documentsController.js](./images/documents-controller.png)

```

### **5.2 Configurar el archivo Dockerfile**

Se crea el archivo `Dockerfile` para construir un contenedor Docker que ejecute la aplicación Node.js.

**Comando utilizado para abrir el archivo:**

```bash
nano Dockerfile
```

**Contenido del archivo `Dockerfile`:**

```dockerfile
# Usar una imagen base de Node.js
FROM node:16

# Configurar el directorio de trabajo en el contenedor
WORKDIR /app

# Copiar los archivos necesarios al contenedor
COPY package*.json ./
COPY src ./src

# Instalar las dependencias
RUN npm install

# Exponer el puerto 3000
EXPOSE 3000

# Comando para ejecutar la aplicación
CMD ["npm", "start"]
```

**Resultado visible en terminal:**

![Contenido del archivo Dockerfile](./images/dockerfile.png)




## **6. Ajustes en Docker y Dependencias**

### **6.1 Actualización del Dockerfile**

Se realiza una configuración adicional en el archivo `Dockerfile` para optimizar el contenedor utilizando una imagen base más ligera y simplificando los comandos de copia.

**Comando utilizado para abrir el archivo:**

```bash
nano Dockerfile
```

**Contenido actualizado del archivo `Dockerfile`:**

```dockerfile
# Imagen base
FROM node:16-alpine

# Configuración del directorio de trabajo
WORKDIR /usr/src/app

# Copiar dependencias y código fuente
COPY package*.json ./
RUN npm install
COPY .

# Exponer el puerto para la aplicación
EXPOSE 3000

# Comando para iniciar el servidor
CMD ["node", "src/index.js"]
```


**Resultado visible en terminal:**

![Actualización del archivo Dockerfile](./images/dockerfile-actualizado.png)



### **6.2 Configurar `docker-compose.yml`**

El archivo `docker-compose.yml` se configura para gestionar el servicio del contenedor, mapeando los puertos y volúmenes necesarios.

**Comando utilizado para abrir el archivo:**

```bash
nano docker-compose.yml
```

**Contenido del archivo `docker-compose.yml`:**

```yaml
version: "3.9"
services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "3000:3000"
    volumes:
      - .:/usr/src/app
      - /usr/src/app/node_modules
    command: ["npm", "start"]
```


**Resultado visible en terminal:**

![Contenido del archivo docker-compose.yml](./images/docker-compose.png)



### **6.3 Instalar Dependencias**

Finalmente, se instalan todas las dependencias necesarias del proyecto utilizando el comando `npm install`, que asegura que todos los módulos especificados en `package.json` estén disponibles para su ejecución.

**Comando utilizado:**

```bash
npm install
```

**Resultado visible en terminal:**

![Instalación de dependencias](./images/npm-install.png)


## **7. Construcción y Pruebas del Contenedor**

### **7.1 Construir la Imagen del Contenedor**

Se ejecuta el comando `docker-compose build` para construir la imagen del contenedor con la configuración establecida en el `Dockerfile`.

**Comando utilizado:**

```bash
sudo docker-compose build
```

**Resultado visible en terminal:**

![Construcción de la imagen del contenedor](./images/docker-compose-build.png)



### **7.2 Iniciar el Contenedor**

Una vez construida la imagen, se utiliza `docker-compose up` para iniciar el contenedor. Esto activa la aplicación en el puerto 3000.

**Comando utilizado:**

```bash
sudo docker-compose up
```

**Resultado visible en terminal:**

![Inicio del contenedor](./images/docker-compose-up.png)



### **7.3 Realizar una Solicitud POST**

Se prueba el endpoint de creación de documentos utilizando `curl`. Este comando envía un objeto JSON con el título y contenido de un documento para almacenarlo en el servidor.

**Comando utilizado:**

```bash
curl -X POST http://localhost:3000/documents \
-H "Content-Type: application/json" \
-d '{"title": "Primer Documento", "content": "Contenido del documento"}'
```

**Resultado visible en terminal:**

![Solicitud POST para crear documento](./images/curl-post.png)



### **7.4 Realizar una Solicitud GET**

Se prueba el endpoint de obtención de documentos con `curl`, verificando que los documentos creados previamente sean devueltos por el servidor.

**Comando utilizado:**

```bash
curl http://localhost:3000/documents
```

**Resultado visible en terminal:**

![Solicitud GET para listar documentos](./images/curl-get.png)


## **8. Gestión de Documentos y Simulación de Vulnerabilidades**

### **8.1 Actualizar un Documento Existente**

Se realiza una prueba con el método HTTP `PUT` para modificar un documento previamente creado. Esto asegura que los datos puedan ser actualizados correctamente.

**Comando utilizado:**

```bash
curl -X PUT http://localhost:3000/documents/1 \
-H "Content-Type: application/json" \
-d '{"title": "Documento Editado", "content": "Nuevo contenido"}'
```

**Resultado visible en terminal:**

![Actualizar documento existente](./images/curl-put-update.png)



### **8.2 Validar los Cambios Realizados**

Se verifica con un método HTTP `GET` que los cambios realizados al documento sean reflejados correctamente.

**Comando utilizado:**

```bash
curl http://localhost:3000/documents
```

**Resultado visible en terminal:**

![Verificar cambios realizados](./images/curl-get-verificado.png)



### **8.3 Intento de Actualización de Documento Inexistente**

Se realiza una prueba para actualizar un documento que no existe en la base de datos. Esto demuestra que el sistema maneja correctamente los errores.

**Comando utilizado:**

```bash
curl -X PUT http://localhost:3000/documents/999 \
-H "Content-Type: application/json" \
-d '{"title": "Intento Fallido", "content": "No debería existir"}'
```

**Resultado visible en terminal:**

![Intento de actualizar documento inexistente](./images/curl-put-error.png)



### **8.4 Introducción de Vulnerabilidades**

Se modifica el archivo `src/index.js` para agregar una ruta vulnerable que simula una inyección SQL. Esto permite realizar pruebas de seguridad en el entorno.

**Comando utilizado:**

```bash
nano src/index.js
```

**Código agregado en `src/index.js`:**

```javascript
app.get('/vulnerable', (req, res) => {
  // Simulación de inyección SQL
  const userInput = req.query.input; // Entrada no validada
  const simulatedQuery = `SELECT * FROM documents WHERE title = '${userInput}'`;
  res.send(`Consulta ejecutada: ${simulatedQuery}`);
});
```

**Resultado visible en terminal:**

![Ruta vulnerable agregada](./images/index-vulnerable.png)



## **10. Análisis de Vulnerabilidades y Riesgos**

### **10.1 Pruebas de Inyección SQL**

Se realizan pruebas para simular inyecciones SQL, un vector de ataque común en aplicaciones web que no validan correctamente las entradas de los usuarios.

#### **Ejecución del Ataque SQL**

```bash
curl "http://localhost:3000/vulnerable?input=' OR '1'='1"
```

En este ejemplo, se introduce un payload para ejecutar una consulta que siempre devuelve verdadero, lo que compromete la base de datos.



### **10.2 Simulación de Ataque XSS**

El siguiente ejemplo demuestra una vulnerabilidad de XSS (Cross-Site Scripting), donde se inyecta código JavaScript malicioso que podría ejecutarse en el navegador del usuario.

#### **Prueba de Inyección XSS**

```bash
curl "http://localhost:3000/xss?input=<script>alert('XSS')</script>"
```

El código inyectado genera una alerta en el navegador, lo que indica que la entrada no fue debidamente sanitizada.



### **10.3 Validación de Consultas SQL**

En esta prueba, se ejecutan dos consultas para observar el comportamiento de la aplicación al recibir entradas válidas y maliciosas.

#### **Ejecución de Consultas**

```bash
curl "http://localhost:3000/vulnerable?input=test"
curl "http://localhost:3000/vulnerable?input=%27%20OR%20%271%27=%271"
```

La primera consulta utiliza un valor válido, mientras que la segunda intenta explotar una inyección SQL.



### **10.4 Exposición de Información Sensible**

En esta etapa, se identifica una fuga de información sensible debido a una mala configuración de los endpoints.

#### **Fuga de Información**

```bash
curl http://localhost:3000/leak
```

El resultado muestra información interna del servidor que podría ser utilizada por un atacante para comprometer la seguridad del sistema.


## **11. Instalación y Configuración de OWASP ZAP**

### **11.1 Instalación de OWASP ZAP**
Para realizar un análisis de vulnerabilidades, se utiliza la herramienta OWASP ZAP. A continuación, se instala en el entorno configurado:

```bash
sudo apt install zaproxy
```

Con este comando se instala OWASP ZAP desde los repositorios oficiales de Kali Linux, asegurando la compatibilidad del sistema.



### **11.2 Iniciar OWASP ZAP**
Una vez instalado, OWASP ZAP se ejecuta utilizando el siguiente comando:

```bash
zaproxy
```

Esto inicia la herramienta y muestra mensajes de configuración por defecto en la consola.



### **11.3 Configuración del Proxy en OWASP ZAP**
En esta etapa, se establece el proxy local en OWASP ZAP. Se configura como `127.0.0.1` con el puerto `8080`. Esto permite capturar y analizar el tráfico de las solicitudes realizadas por el navegador.

#### Configuración del Proxy en ZAP:
- Navegar a: `Local Servers/Proxies` en la interfaz de OWASP ZAP.
- Ingresar los valores:
  - **Address:** `127.0.0.1`
  - **Port:** `8080`

#### Vista de Configuración del Proxy:
![Configuración del Proxy en OWASP ZAP](file-H3NoHirMo1XhLX1hWbdwem.png)



### **11.4 Configuración del Proxy en el Navegador**
Para que OWASP ZAP capture el tráfico, es necesario configurar el navegador para usar el proxy local configurado. Los pasos son los siguientes:

1. Ir a la configuración de red del navegador.
2. Seleccionar "Configuración manual del proxy".
3. Configurar los campos:
   - **HTTP Proxy:** `127.0.0.1`
   - **Port:** `8080`
   - Habilitar "Also use this proxy for HTTPS".
4. Confirmar los cambios y aplicar la configuración.

#### Vista de Configuración en el Navegador:
![Configuración del Proxy en el Navegador](file-W2Q9ZHSg8KQVviDFgENtw7.png)

Esto asegura que todas las solicitudes HTTP(S) pasen a través de OWASP ZAP, permitiendo su análisis y prueba.


## **12. Configuración de Proxy y Exploración de Vulnerabilidades**

### **12.1 Desactivación de OCSP Stapling en Firefox**

Se realiza la configuración en el navegador Firefox para deshabilitar el OCSP Stapling. Esto permite que las pruebas con ZAP no tengan conflictos relacionados con certificados. 

```bash
about:config
```

1. En la barra de búsqueda, escriba `security.ssl.enable_ocsp_stapling` y cambie su valor a `false`. Esto asegura que Firefox no valide los certificados usando OCSP durante las pruebas.
2. Este ajuste es temporal y debe ser revertido después de las pruebas.

**Captura:**
![Configuración de OCSP Stapling](file-APV31vv5oGsuNt8uKAWXNz)


### **12.2 Configuración de Sitios en ZAP**

En ZAP, se agregaron los sitios relevantes detectados para su análisis. Esto permite estructurar mejor la información recolectada durante las pruebas de penetración.

```bash
# En ZAP:
# Navegar por los sitios detectados en el árbol del escáner.
```

1. En la sección de "Sites" de ZAP, los sitios relevantes son listados, incluyendo dominios específicos.
2. Estos sitios son analizados posteriormente con herramientas específicas.

**Captura:**
![Sitios Configurados](file-THfHfcH7sWdqMUQeAAmsQ4)



### **12.3 Uso del Spider Tradicional y AJAX**

Se ejecuta un spider (explorador web) sobre el sitio objetivo para identificar posibles puntos de vulnerabilidad.

```bash
# Configuración y ejecución del spider en ZAP
```

1. Se selecciona la opción "Traditional Spider" para rastrear el sitio objetivo.
2. Opcionalmente, se habilita el "AJAX Spider" para analizar interacciones dinámicas en sitios web.
3. Se inicia el análisis con el botón `Attack`.

**Captura:**
![Spider en Proceso](file-8DUakVSRhXGyvD56UXU72m)



### **12.4 Resultados del Escaneo**

Después del análisis, ZAP proporciona una lista de alertas de seguridad identificadas en el sitio objetivo.

```bash
# Navegación de alertas de ZAP
```

1. Se visualizan las vulnerabilidades detectadas, como encabezados HTTP ausentes o fugas de información.
2. Estas alertas proporcionan detalles y posibles soluciones para mitigar riesgos.

**Captura:**
![Alertas Detectadas](file-CDbDAwPkzNtqErEMmDoZ9f)




## **Resumen de las Vulnerabilidades Detectadas**

A continuación, se presenta un resumen detallado de las vulnerabilidades identificadas durante la ejecución de las pruebas de seguridad con las herramientas configuradas. Cada vulnerabilidad se describe con sus características principales, impacto, y nivel de criticidad según las métricas CVSS.



### **Tabla de Vulnerabilidades Detectadas**

| **Vulnerabilidad**                   | **Descripción**                                                                                       | **Impacto**                | **Nivel de Criticidad (CVSS v4.0)** |
|````````````````````````````````````--|``````````````````````````````````````````````````````````````````````````````````````````````````````-|```````````````````````````-|````````````````````````````````````|
| **X-Content-Type-Options Header Missing** | El servidor no envía el encabezado de respuesta `X-Content-Type-Options`, exponiendo a ataques de inyección de contenido. | Exposición a ataques XSS   | **Medio (6.9)**                   |
| **Server Leaks Version Information** | El servidor expone información de su versión en los encabezados de respuesta, lo que facilita ataques dirigidos. | Información sensible       | **Medio (6.5)**                   |
| **Inyección SQL (SQLi)**             | Entrada de usuario no validada que permite manipular las consultas SQL ejecutadas por el servidor.      | Compromiso de la base de datos | **Crítico (9.1)**                |
| **Cross-Site Scripting (XSS)**       | El servidor refleja directamente entradas maliciosas, permitiendo la ejecución de código JavaScript en el navegador del usuario. | Robo de sesiones           | **Alto (8.8)**                    |
| **Información de Configuración Expuesta** | Archivos de configuración expuestos a través de rutas no protegidas.                                   | Acceso a variables sensibles | **Crítico (9.0)**                |



### **Métricas de Impacto CVSS v4.0**

#### **Exploitability Metrics**
- **Attack Vector (AV):** `Network (N)`
- **Attack Complexity (AC):** `Low (L)`
- **Attack Requirements (AT):** `None (N)`
- **Privileges Required (PR):** `None (N)`
- **User Interaction (UI):** `None (N)`

#### **Vulnerable System Impact Metrics**
- **Confidentiality (VC):** `Low (L)`
- **Integrity (VI):** `Low (L)`
- **Availability (VA):** `Low (L)`



### **Conclusiones**

- La mayoría de las vulnerabilidades detectadas tienen un nivel de criticidad medio a alto, requiriendo atención inmediata para su mitigación.
- Las configuraciones incorrectas, como la ausencia de encabezados de seguridad, exponen el sistema a ataques comunes como XSS y SQLi.
- Es fundamental reforzar las medidas de seguridad, como validar entradas de usuario, proteger rutas sensibles y configurar correctamente los encabezados de respuesta HTTP.





## **Integración de Seguridad en el Pipeline CI/CD**

La integración de la seguridad en los pipelines de CI/CD es esencial para garantizar que las aplicaciones y sus entornos de ejecución se mantengan protegidos durante todo el ciclo de vida del desarrollo. A continuación, se describe un proceso detallado que integra herramientas y estrategias en las diferentes fases del pipeline.



### **1. Configuración de Validaciones Automáticas**

#### **Herramientas a Usar**
- **OWASP ZAP:** Para análisis dinámico de seguridad (DAST).
- **Trivy:** Para escanear vulnerabilidades en dependencias y contenedores.
- **SonarQube:** Para análisis estático de código (SAST).



#### **Proceso en el Pipeline**

##### **1.1 Fase de Build (Compilación)**
- Ejecuta análisis estático (SAST) con **SonarQube** para identificar vulnerabilidades en el código fuente.
- Comando de ejemplo:
```bash
sonar-scanner \
  -Dsonar.projectKey=nombre_proyecto \
  -Dsonar.sources=./src \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=tu_token
```

##### **1.2 Fase de Testing**
- Escanea las dependencias y contenedores con **Trivy**.
- Comando de ejemplo:
```bash
trivy fs ./ --severity CRITICAL,HIGH --exit-code 1 --format table
```
- Este comando fallará la compilación si se detectan vulnerabilidades críticas o altas.

##### **1.3 Fase de Despliegue (Deploy)**
- Ejecuta análisis dinámico (DAST) con **OWASP ZAP** para identificar vulnerabilidades en la aplicación en ejecución.
- Comando de ejemplo:
```bash
zap.sh -quickurl http://localhost:3000 -quickout zap_report.html
```



### **2. Estrategias de Remediación**

#### **a) Parches**
1. Implementa una política para aplicar parches críticos automáticamente a las dependencias.
   - Usa herramientas como **Dependabot** (GitHub) o **Renovate** para actualizar dependencias automáticamente.
2. Configura revisiones obligatorias para dependencias de alto riesgo antes de aprobar los cambios.

#### **b) Configuración Segura**
1. Crea scripts de infraestructura como código (IaC) con herramientas como **Terraform** o **Ansible** para garantizar configuraciones seguras.
   - Ejemplo de validación de configuración:
```bash
terraform validate
```
   - Escaneo de configuraciones inseguras:
```bash
checkov -d ./infra
```

#### **c) Refactorización de Código**
1. Incluye revisiones de código centradas en la seguridad en cada pull request.
2. Usa **SonarQube** para identificar patrones de código que puedan ser refactorizados.
3. Asegúrate de incluir pruebas automatizadas de seguridad como parte de la suite de testing.


### **3. Alertas Automatizadas para Nuevas Vulnerabilidades**

#### **3.1 Implementación de Alertas**
- Configura herramientas de escaneo continuo, como **Trivy** o **OWASP Dependency-Check**, para ejecutar análisis programados y notificar sobre vulnerabilidades nuevas.

#### **3.2 Notificaciones**
- Usa herramientas de comunicación como **Slack**, **Microsoft Teams**, o **email** para alertar automáticamente sobre vulnerabilidades detectadas.
- Ejemplo con **Slack** usando un webhook:
```bash
curl -X POST -H 'Content-type: application/json' \
  --data '{"text":"Se detectaron vulnerabilidades críticas en el pipeline CI/CD."}' \
  https://hooks.slack.com/services/tu_webhook
```

#### **3.3 Integración con Sistemas de Seguimiento**
- Configura integración con **Jira** o **Azure DevOps** para crear automáticamente tickets de remediación cuando se detecten vulnerabilidades críticas.


Este proceso establece un enfoque proactivo y automatizado para garantizar la seguridad en todas las fases del pipeline CI/CD, reduciendo significativamente el riesgo de vulnerabilidades explotables.

# **Configuración Completa del Pipeline CI/CD**

## **1. Creación del Archivo del Pipeline**
### **1.1 Creación del directorio y archivo YAML**
Se crea el directorio `.github/workflows` y el archivo `ci-pipeline.yml` para definir las acciones del pipeline CI/CD.

```bash
mkdir -p .github/workflows
touch .github/workflows/ci-pipeline.yml
```


## **2. Contenido del Archivo del Pipeline**
El archivo YAML configura un pipeline con etapas de construcción, análisis y despliegue.

```yaml
name: DevSecOps CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build-and-scan:
    runs-on: ubuntu-latest

    steps:
      # 1. Clonar el repositorio
      - name: Checkout code
        uses: actions/checkout@v3

      # 2. Configurar Node.js
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '16'

      # 3. Instalar dependencias
      - name: Install dependencies
        run: npm install

      # 4. Escanear dependencias y contenedores con Trivy
      - name: Run Dependency Scan with Trivy
        run: |
          curl -sSfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sh -
          trivy fs ./ --severity CRITICAL,HIGH --exit-code 1 --format table

      # 5. Construir la imagen Docker
      - name: Build Docker image
        run: docker build -t devsecops-app .

      # 6. Ejecutar DAST con OWASP ZAP
      - name: Run DAST with OWASP ZAP
        run: |
          docker run -d -p 8080:8080 --name zap owasp/zap2docker-stable zap.sh
          sleep 10
          docker exec zap zap-cli quick-scan --self-contained --spider http://localhost:3000
```


## **3. Inicialización del Repositorio Git**
Se inicializa el repositorio Git y se configura la rama predeterminada como `main`.

### **3.1 Inicialización del repositorio**

```bash
git init
```

### **3.2 Configuración de la rama principal como 'main'**

```bash
git branch -m main
git config --global init.defaultBranch main
```



## **4. Preparación de los Cambios para el Repositorio**
Se agregan los cambios al índice y se realiza el commit inicial.

### **4.1 Agregar todos los archivos al índice**

```bash
git add .
```

### **4.2 Realizar el commit inicial**

```bash
git commit -m "Initial commit"
```


