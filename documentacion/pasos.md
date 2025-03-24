# 🚀 Documentación Oficial del Proyecto: Plataforma de Cursos Online

Este proyecto tiene como objetivo desarrollar una Plataforma de Cursos Online, construida sobre un entorno Docker, con backend en PHP y base de datos PostgreSQL.

## 📂 Estructura del Proyecto

    proyectoDB/
    ├── backend/
    ├── documentacion/
    │   ├── imagenes/
    │   │   ├── crear_repositorio.png
    │   │   ├── docker_compose.png
    │   │   └── ...
    │   ├── pasos.md
    │   └── base_de_datos.md
    ├── docker-compose.yml
    └── README.md              


## ✅ Instrucciones Paso a Paso

### 1. Crear un Nuevo Repositorio en GitHub
- Ve a tu cuenta de GitHub y crea un nuevo repositorio. Nombre del Proyecto: ProyectoDB.
- Añade un archivo README.md inicial describiendo el propósito del proyecto.

### 2. Clonar el Repositorio en tu Máquina Local

    git clone <URL-del-repositorio>
    cd ProyectoDB

![imagen](./imagenes/1_clonar_repo_local.png)

### 3. Crear un Proyecto Sencillo de Base de Datos con Docker

![imagen](./imagenes/crear_docker_composer.png)

![imagen](./imagenes/editar_docker_compose.png)

imagen de doker composer 2 (pendiente subir)

### 4. Levantar el Contenedor PostgreSQL con Docker

    docker-compose up -d

![imagen](./imagenes/levantar_proyecto.png)


### 5. Crear Ramas y Hacer Commits

    git checkout -b feature/database-setup

![imagen](./imagenes/Crear_rama.png)

#### - Realiza cambios y guarda commits:

![imagen](./imagenes/Cambios_en_rama.png)

#### - Sube tu rama a GitHub:

      git push -u origin feature/database-setup

![imagen](./imagenes/subida_archivos.png)

### 7. Conectar PostgreSQL con DBeaver

#### Instalar PostgreSQL
![imagen](./imagenes/instalar_postgres_2.png)

#### Comprobar estado de PostgreSQL
![imagen](./imagenes/instalar_postgres_3_comrprobar_estado.png)

#### Comprobar puerto de uso de PostgreSQL
![imagen](./imagenes/instalar_postgres_4_comprueba_puerto.png)

#### Crea usuario en PostgreSQL
![imagen](./imagenes/Crea_user_postgres_1.png)

#### Dar al usuario permisos de súper usuario
![imagen](./imagenes/superusuario.png)

#### Probar conexión en DBeaver
![imagen](./imagenes/probar_concexion_dbeaver_1.png)

![imagen](./imagenes/probar_conexion_dbeaver_2.png)


### 8. Diseñar base de datos del proyecto y un Diagrama Entidad-Relación (ERD)

#### - Proyecto elegido: Plataforma de Cursos Online.
#### - Entidades: usuarios, cursos, lecciones, evaluaciones, inscripciones, certificados.

![imagen](./imagenes/diagrama_ER.png)

➡️ Ver la documentación completa de la Base de Datos aquí:
👉 ./base_de_datos.md


9. Subir Cambios a GitHub
- Fusiona la rama feature/database-setup con main:

    git checkout main
    git merge feature/database-setup
    git push

- Imagen: ./imagenes/fusionar_ramas.png
