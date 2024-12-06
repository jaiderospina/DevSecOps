## Taller Escaner Vulneravilidades

## Integrantes Grupo


> - Ingrid Paola Quiroga
> - Juan Alvarez
> - Brayan Hernandez
> - Monica Florez Mejia
> - Alejandro Cortes
> - Charles Guerrero

## Tabla de Contenido

## Introducción
> - 1.1.  ¿Qué es OpenVAS?
> - 1.2. Características clave:
> - 1.3. Para que se utiliza

## Metodos Utilizados para la instalacion de Open Vas
> - 2.1.  Instalación desde nube EC2
> - 2.2.  Dockerizacion
> - 2.3.  Maquina Virtual en linux

## Conclusiones y Recomendaciones
> - 5.1. Conclusiones



## ¿Qué es OpenVAS?

OpenVAS (Open Vulnerability Assessment System) es una herramienta de código abierto utilizada para realizar evaluaciones de seguridad y escaneos de vulnerabilidades en sistemas informáticos, redes y aplicaciones. Su objetivo es identificar posibles debilidades y riesgos de seguridad que puedan ser explotados por atacantes.
OpenVAS puede escanear:

Redes: Detecta configuraciones incorrectas o vulnerabilidades en routers, switches y otros dispositivos de red.
Sistemas Operativos: Examina máquinas con sistemas operativos como Linux, Windows o macOS en busca de fallos de seguridad.
Aplicaciones Web y Servicios: Evalúa aplicaciones web, servidores web, bases de datos, y otros servicios en busca de vulnerabilidades.



## Características clave:

Escaneo de Vulnerabilidades: OpenVAS realiza escaneos exhaustivos buscando vulnerabilidades conocidas en dispositivos, redes y aplicaciones.

Interfaz Gráfica: Ofrece una interfaz fácil de usar a través de Greenbone Security Assistant (GSA) para gestionar y visualizar los resultados de los escaneos.

Base de Datos Actualizada: OpenVAS cuenta con una extensa base de datos con más de 50,000 pruebas de vulnerabilidad, que se actualiza constantemente.


Gratuito y de código abierto.
Actualizaciones frecuentes para detectar vulnerabilidades nuevas.
Escaneos detallados y análisis profundo de la seguridad.



## ¿Para qué se utiliza?

Evaluación de redes: Identificar vulnerabilidades en routers, switches y dispositivos de red.
Auditoría de sistemas operativos: Analizar máquinas con sistemas como Linux, Windows o macOS.
Escaneo de aplicaciones web: Detectar fallos en servidores y aplicaciones web.




# Metodos de instalación OpenVas que usamos:

## 1. Instalación desde nube EC2

![image](https://github.com/user-attachments/assets/19109612-e85f-446c-a8de-60a852155ce6)


Creamos una instancia ec2 de Amazon 
![image](https://github.com/user-attachments/assets/e59a6ef4-b49c-44d2-9e30-be679395147a)


Nos conectamos por ssh 
![image](https://github.com/user-attachments/assets/3b09b7e3-f06d-4f4c-a60d-c78a0c7af1cf)



Habilitamos puertos de comunicación 
![image](https://github.com/user-attachments/assets/b6f75571-3612-4c75-bc89-727b1380e95c)




## 2. Dockerizacion

## 1. Inicio del Escaneo:
Configuración del Escaneo: Se configura el escaneo en OpenVAS, donde seleccionas el objetivo (la IP o rango de IPs), el tipo de escaneo y las políticas de seguridad (por ejemplo, si quieres realizar un escaneo rápido o profundo).
Selección de pruebas (NVTs): OpenVAS utiliza pruebas conocidas como NVTs (Network Vulnerability Tests), que son scripts diseñados para detectar vulnerabilidades específicas en servicios, aplicaciones y sistemas operativos. Estas pruebas están basadas en una base de datos de vulnerabilidades conocida y se actualizan frecuencia.

1. Creamos una carpeta y la abrimos con visual studio.  

con los presentes comandos descargamos el archivo docker-compose.yaml y lo corremos 
![image](https://github.com/user-attachments/assets/77e4f2e8-e449-4d59-aee4-7a54dae599db)


2. Acá visualizamos la descarga del archivo docker-compose.yml

![image](https://github.com/user-attachments/assets/8fba0da1-5939-4582-b5d0-e3d483d3eb9b)
![image](https://github.com/user-attachments/assets/cb564c87-9cdb-4366-b31a-05ead005ea77)



3.aca verificamos la ejecucion de los contenedores  
![image](https://github.com/user-attachments/assets/ee04f7d1-f585-4288-aef0-3e55ace1e6fc)


4.ingresando a la url podemos visualizar es dashboard de openvas 

![image](https://github.com/user-attachments/assets/bb8e41ad-54d2-4aa6-8926-6f2d78239fa9)

![image](https://github.com/user-attachments/assets/389e1ac9-0e53-45fb-8d09-1810c8ec203d)

5.corremos el contenedor con vulnerabilidades

![image](https://github.com/user-attachments/assets/e03d9446-820d-44af-9312-55f31b7d5b1b)


Cuando escaneamos una vulnerabilidad con OpenVAS, el proceso implica varias etapas clave para detectar y evaluar posibles fallos de seguridad en el sistema objetivo. Aquí te explico qué sucede paso a paso durante el escaneo


## 3. Maquina virtual Linux

![image](https://github.com/user-attachments/assets/727a8d4f-40d9-4e54-aa2b-dde2252e001e)












## Conclusión:

OpenVAS es una herramienta esencial para la gestión de seguridad en infraestructuras IT, permitiendo detectar vulnerabilidades antes de que los atacantes puedan explotarlas. Es ideal para profesionales de seguridad que buscan una solución poderosa y gratuita para proteger sus sistemas y redes.






