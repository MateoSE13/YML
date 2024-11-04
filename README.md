# 1. Título
Generación de Contenedores usando Docker Compose con Archivos YAML: PostgreSQL y PgAdmin

# 2. Tiempo de duración
20 minutos

# 3. Fundamentos
Docker Compose es una herramienta que permite definir y ejecutar aplicaciones en Docker con múltiples contenedores usando un archivo de configuración YAML. En esta práctica, se utilizará Docker Compose para desplegar dos contenedores: uno con PostgreSQL, un sistema de gestión de bases de datos, y otro con PgAdmin, una interfaz de administración gráfica para PostgreSQL.

PostgreSQL es un sistema de bases de datos relacional y altamente robusto, mientras que PgAdmin es una herramienta visual que facilita la administración de bases de datos en PostgreSQL. Esta práctica simplificará la configuración y conexión entre estos dos contenedores mediante Docker Compose, permitiendo un entorno de base de datos funcional en pocos pasos.

### Conceptos clave:
- **Docker**: Plataforma que permite ejecutar aplicaciones en contenedores aislados.
- **Docker Compose**: Herramienta para configurar múltiples contenedores mediante archivos YAML.
- **PostgreSQL**: Sistema de bases de datos relacional.
- **PgAdmin**: Interfaz de administración gráfica para PostgreSQL.

# 4. Conocimientos previos
- Comandos básicos en Docker y Docker Compose.
- Conceptos de bases de datos.
- Familiaridad con YAML para la configuración.

# 5. Objetivos a alcanzar
- Configurar un contenedor para PostgreSQL y otro para PgAdmin usando Docker Compose.
- Persistir datos de PostgreSQL en un volumen para asegurar su durabilidad.
- Exponer puertos para acceder a PgAdmin a través de un navegador.

# 6. Equipo necesario
- Computadora con Docker y Docker Compose instalados.
- Cuenta en Docker Hub para obtener las imágenes de contenedores.

# 7. Material de apoyo
- Documentación oficial de Docker Compose.
- Guía básica de comandos Docker.
- Documentación de PostgreSQL y PgAdmin para configuraciones avanzadas.

# 8. Procedimiento

### Paso 1: Crear el archivo `docker-compose.yml`
En el directorio de tu proyecto, crea un archivo llamado `docker-compose.yml` con el siguiente contenido para configurar los servicios de PostgreSQL y PgAdmin:

![image](https://github.com/user-attachments/assets/63b5638c-600b-49b5-93de-b6db1f8ad242)


Descripción de la Configuración
db: Este servicio utiliza la imagen de PostgreSQL y configura un usuario, una contraseña y una base de datos inicial. La base de datos se persiste en un volumen (postgres_data) para asegurar la durabilidad de los datos.
pgadmin: Este servicio utiliza la imagen de PgAdmin, configurando credenciales de acceso. PgAdmin depende del servicio db, lo que asegura que PostgreSQL esté listo antes de iniciar PgAdmin.


### Paso 2: Iniciar los contenedores
Desde el terminal, navega hasta el directorio donde creaste el archivo docker-compose.yml y ejecuta el siguiente comando para iniciar los contenedores:
![image](https://github.com/user-attachments/assets/13488bf5-692b-4e54-a2b2-a3d901db40f9)
El indicador -d ejecuta los contenedores en segundo plano.


### Paso 3: Verificar que los contenedores estén en ejecución
Para asegurarte de que ambos contenedores están corriendo, utiliza el comando:
`docker ps`
![image](https://github.com/user-attachments/assets/c20beddd-80a3-4e88-b468-75a8f92618d6)

### Paso 4: Acceso a PgAdmin
Abre un navegador y accede a http://localhost:5050. Inicia sesión con el email y la contraseña configurados en docker-compose.yml (admin@example.com / practica1).
![image](https://github.com/user-attachments/assets/9211fd0b-9f19-40c3-afa2-10c57c757d92)

### Paso 5: Conectar PgAdmin a PostgreSQL
En la interfaz de PgAdmin, crea una nueva conexión de servidor con los siguientes datos:
![image](https://github.com/user-attachments/assets/80351b0c-3d0c-41be-bfa4-2eb3354d4886)

### Paso 6. Resultados esperados
Al finalizar la práctica, debería tener un contenedor PostgreSQL y un contenedor PgAdmin en ejecución. PgAdmin debería conectarse correctamente a la base de datos PostgreSQL, permitiéndo administrar la base de datos desde una interfaz gráfica.

### Paso 7 Bibliografía
Merkel, D. (2014). Docker: Lightweight Linux Containers for Consistent Development and Deployment. Linux Journal, 2014(239), 2.
Kane, A. (2024). Docker in Action, Second Edition. Manning Publications.
Pahl, C., & Brogi, A. (2016). Cloud Container Technologies: A State-of-the-Art Review. IEEE Transactions on Cloud Computing, 5(4), 667-678.







