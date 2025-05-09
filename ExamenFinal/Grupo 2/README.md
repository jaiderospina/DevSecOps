Adriana Tobon Davila 

      Evaluación y Priorización de Vulnerabilidades en un Entorno DevSecOps mediante CVSS 4.0

      
Se debe implementar un entorno de desarrollo ágil con un repositorio de código con una aplicación web básica, usamos WSL para entrar al entorno.
![image](https://github.com/user-attachments/assets/5e0a35ab-bc79-4d35-a369-be1c8cf03b83)

Se crea el entorno de desarrollo laravel.
![image](https://github.com/user-attachments/assets/8d03db56-6be4-4158-aa2e-b922780910d7)

Se crea la imagen con laravel.
![image](https://github.com/user-attachments/assets/0c575586-6626-4635-b7d5-5e6cf0608aff)

Instalación del contenedor de la base de datos
![image](https://github.com/user-attachments/assets/2383d12f-278d-43db-b488-fa5aecd636cd)
![image](https://github.com/user-attachments/assets/fbef7d0d-7982-4e06-a2ff-841737dbf901)
![image](https://github.com/user-attachments/assets/de0e4e1a-701a-4f9d-8237-184d6621c508)
![image](https://github.com/user-attachments/assets/f556921b-b983-48cd-ab70-c65fcd3bba22)


Se crea un Commit a GITHUB
![image](https://github.com/user-attachments/assets/44aba3be-98f6-4f37-a16a-341e7cacaaed)

Creación de repositorio y conexión en GITHUB
![image](https://github.com/user-attachments/assets/eb66932a-894e-4c4f-bb11-25efbb89fd42)

Subir los archivos al repositorio remoto:
![image](https://github.com/user-attachments/assets/3ca38576-faa8-4a9b-b3dc-4c184474a48c)

Los documentos del proyecto se subieron al repo de forma correcta, sistema de CI/CD y se crean 2 branch con el fin de identificar los cambios que se hagan en la rama DEV y  pasarlos a la rama main si se considera que el código es seguro para ejecutarlo.

![image](https://github.com/user-attachments/assets/ef34e6b2-1533-4330-b081-b43f80d75d72)

se realiza la creación del workflow
![image](https://github.com/user-attachments/assets/542ace75-afdc-42d3-927d-b2552cc9cdf2)
![image](https://github.com/user-attachments/assets/bd269c78-d6b9-4eb1-beab-e15d8f0a9a27)

hacemos git para agregar al repositorio de Github
![image](https://github.com/user-attachments/assets/84f4c956-98bc-4773-87cd-587d10b66906)

identificar vulnerabilidades en el código anteriormente, se procede a utilizar la herramienta 
Snyk, la cual nos permitirá evaluar las vulnerabilidades y posteriormente corregirlas.
![image](https://github.com/user-attachments/assets/ab9cdf02-7f3a-48e0-a346-45db73523452)

Se instala snyk con visual code para evidenciar las vulnerabilidades y se ve el resultado 
del escaneo de vulnerabilidades con Snyk en VS con el código con vulnerabilidades.
![image](https://github.com/user-attachments/assets/a1931319-a0c5-4eb8-9ff7-6eae7adf940c)

Se verifica en Snyk y se identifica el total de vulnerabilidades encontradas en el código.
![image](https://github.com/user-attachments/assets/eceb7ab3-6588-4be8-a879-03ec02e7c73a)

Use of Hard-coded Credentials (CWE-798) es una vulnerabilidad en el desarrollo web que consiste en incrustar credenciales, como nombres de usuario y contraseñas, en el código fuente de una aplicación o sistema web
![image](https://github.com/user-attachments/assets/6a4548bd-dba5-454c-8cdb-595a345ce6a0)









