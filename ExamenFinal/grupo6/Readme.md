#Integrantes: 
- Erik Celis
- Diego Padilla
- Diego Sindicue

![Texto alternativo](ExamenFinal/grupo6/1.png)
![Texto alternativo](ExamenFinal/grupo6/2.png)
![Texto alternativo](ExamenFinal/grupo6/3.png)
![Texto alternativo](ExamenFinal/grupo6/4.png)
![Texto alternativo](ExamenFinal/grupo6/5.png)
![Texto alternativo](ExamenFinal/grupo6/6.png)
![Texto alternativo](ExamenFinal/grupo6/7.png)

# DevSecOps

Aplicación web creada con Flask para publicar noticias relacionadas con DevSecOps.

## Descripción

Este es un sitio web donde se publican noticias relacionadas con DevSecOps. Está construido con Flask y tiene un diseño sencillo y funcional. El objetivo es proporcionar contenido relevante sobre seguridad y desarrollo de software.

## Requisitos

- Python 3.9 o superior
- Docker (opcional, si deseas usar contenedores)
- Pip (para instalar las dependencias)

## Instalación

Para instalar y ejecutar el proyecto en tu máquina local, sigue estos pasos:

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/mi-proyecto-flask.git
   cd mi-proyecto-flask
   ```

2. Instala las dependencias necesarias:
   ```bash
   pip install -r requirements.txt
   ```

3. Ejecuta la aplicación:
   ```bash
   python app.py
   ```

Si prefieres usar **Docker**, puedes ejecutar los siguientes comandos para construir y ejecutar la aplicación en un contenedor:

```bash
docker build -t mi-proyecto-flask .
docker run -p 5000:5000 mi-proyecto-flask


### 5. **Ejecución de Pruebas**
- Describe cómo ejecutar las pruebas unitarias.

```markdown
## Pruebas

El proyecto incluye pruebas unitarias para verificar que la aplicación funciona correctamente.

Para ejecutar las pruebas, usa el siguiente comando:

```bash
python -m unittest discover -s app/tests


### 6. **Docker (Opcional)**
- Proporciona instrucciones detalladas sobre cómo usar Docker para ejecutar la aplicación dentro de un contenedor.

```markdown
## Uso de Docker (Opcional)

Si prefieres ejecutar el proyecto usando Docker, puedes construir y ejecutar el contenedor con los siguientes comandos:

1. Construye la imagen de Docker:
   ```bash
   docker build -t mi-proyecto-flask .
   ```

2. Ejecuta la aplicación en un contenedor Docker:
   ```bash
   docker run -p 5000:5000 mi-proyecto-flask
   ```

3. Accede a la aplicación en [http://localhost:5000](http://localhost:5000).

## CI/CD

Este proyecto usa **GitHub Actions** para la integración continua y el despliegue continuo.

El flujo de trabajo está configurado para ejecutarse en la rama `main` y realizar las siguientes acciones:

1. **Checkout del código**: Descarga el código más reciente desde el repositorio.
2. **Configuración de Python**: Establece la versión de Python (3.9 en este caso).
3. **Instalación de dependencias**: Instala las dependencias necesarias usando `pip`.
4. **Pruebas**: Ejecuta las pruebas unitarias con `unittest` para asegurarse de que todo funcione correctamente.

El archivo de flujo de trabajo está configurado en `.github/workflows/ci.yml`.

## Estructura del Proyecto

La estructura de archivos del proyecto es la siguiente:


- **`app/`**: Contiene la aplicación Flask.
  - `app.py`: El archivo principal de la aplicación Flask.
  - `requirements.txt`: Las dependencias del proyecto.
  - `tests/`: Carpeta con los archivos de prueba, como `test_app.py`.

- **`.github/`**: Contiene los flujos de trabajo de CI/CD configurados con GitHub Actions.

- **`Dockerfile`**: Define la configuración del contenedor Docker.

- **`index.html`**: El archivo HTML principal que se muestra cuando se accede a la aplicación.

- **`README.md`**: Este archivo, que documenta el proyecto.

