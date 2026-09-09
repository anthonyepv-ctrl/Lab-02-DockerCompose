# LABORATORIO 02 

Hoy utilizaremos docker compose para poder desplegar un servicio web y una base de datos, para ello usaremos el siguiente STACK Tecnico:

## 1. API:
   
- **Repositorio:** La presente API se extrajo del repositorio de Dockerhub en cual se puede encontrar en el siguiente enlace https://hub.docker.com/r/nmatsui/hello-world-api.
- **Proceso de despliegue:** La creación de las imagenes y ejecución de contenedores se realiza de forma automatica mediante el archivo "docker-compose.yaml", el cual verifica el archivo Dockerfile de la carpeta api/.
- **Resultado de despliegue:** Al ejecutar docker compose (revisar el apartado de comando para verificar como se ejecuta) se despliega exitosamente las 3 copias de la API en segundo plano, para verificar el despliegue ingrese a las siguientes url: `http://localhost:3000`, `http://localhost:3001`, `http://localhost:3002`

## 2. BD PostgreSQL:

- **Imagen:** `postgres:13` (oficial de Docker Hub).
 - **Configuración mediante Variables de Entorno:**
  - `POSTGRES_DB`: Nombre de la base de datos, mapeado desde la variable `${POSTGRES_DB_NAME}`.
  - `POSTGRES_USER`: Usuario de la base de datos, mapeado desde la variable `${POSTGRES_DB_USER}`.
  - `POSTGRES_PASSWORD`: Contraseña de acceso, mapeada desde la variable `${POSTGRES_DB_PASSWORD}`.
 - **Seguridad:** Los valores de estas variables se gestionan de forma segura a través del archivo .env (el cual por obvias razones se prohibe subir al repositorio en github mediante el archivo .gitignore, pero existe un archivo .env.example para ver como se estructuran las variables de entorno).
 
## 3. Comandos:

- **Para clonar este repositorio se tiene que ejecutar:** git clone https://github.com/anthonyepv-ctrl/Lab-02-DockerCompose 

- **Configurar las variables de entorno:** 
(Windows) copy .env.example .env 
(Linux/MacOS) cp .env.example .env
*Nota: Modificar los datos de las varaibles de entorno a sus datos personales.

- **Despliegue con Docker Compose:** docker compose up -d (Despliega las 3 copias de la API y la BD PostgresSQL en segundo plano).

- **Verificar estado de los contenedores:** docker compose ps

- **Remover los contenedores:** docker compose down 

## 4. Configuraciones:

