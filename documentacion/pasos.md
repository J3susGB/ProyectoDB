🚀 Documentación Oficial del Proyecto: Plataforma de Cursos Online

Este proyecto tiene como objetivo desarrollar una Plataforma de Cursos Online, construida sobre un entorno Docker, con backend en PHP y base de datos PostgreSQL.

📂 Estructura del Proyecto

proyecto/
├── backend/                  # Código fuente PHP
├── documentacion/            # Documentación del proyecto
│   ├── imagenes/             # Capturas de pantalla usadas en la documentación
│   ├── pasos.md              # Guía paso a paso (este archivo)
│   └── base_de_datos.md      # Documentación de la Base de Datos
├── docker-compose.yml        # Definición de los servicios Docker
└── README.md                 # Descripción general del proyecto


✅ Instrucciones Paso a Paso

1. Crear un Nuevo Repositorio en GitHub
- Ve a tu cuenta de GitHub y crea un nuevo repositorio. Ejemplo de nombre: ProyectoDB.
- Añade un archivo README.md inicial describiendo el propósito del proyecto.
- Imagen: ./imagenes/crear_repositorio.png

2. Clonar el Repositorio en tu Máquina Local

git clone <URL-del-repositorio>
cd ProyectoDB

- Imagen: ./imagenes/clonar_repositorio.png

3. Crear un Proyecto Sencillo de Base de Datos con Docker
- Crea el archivo docker-compose.yml para levantar el contenedor de PostgreSQL.

Ejemplo:

version: '3.8'
services:
  db:
    image: postgres:latest
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: proyectodb
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data

volumes:
  postgres-data:

- Imagen: ./imagenes/docker_compose.png


4. Levantar el Contenedor PostgreSQL con Docker

docker-compose up -d

- Imagen: ./imagenes/levantar_contenedor.png


5. Crear Ramas y Hacer Commits
- Crea una nueva rama para el desarrollo de la base de datos:

git checkout -b feature/database-setup

- Realiza cambios y guarda commits:

git add .
git commit -m "feat(database): add PostgreSQL setup with Docker Compose"

- Sube tu rama a GitHub:

git push -u origin feature/database-setup

- Imagen: ./imagenes/crear_ramas_commits.png


6. Practicar Rollbacks en Git

- Deshacer el último commit:

git reset --soft HEAD~1

- Volver a un commit anterior:

git checkout <ID-del-commit>

- Revertir un commit:

git revert <ID-del-commit>

- Borrar una rama remota:

git push origin --delete nombre-rama

- Imagen: ./imagenes/practicar_rollbacks.png


7. Conectar PostgreSQL con DBeaver
1. Abre DBeaver y crea una nueva conexión.
2. Datos de la conexión:
- Host: localhost
- Puerto: 5432
- Database: proyectodb
- User: user
- Password: password

3. Haz clic en Test Connection.

- Imagen: ./imagenes/conexion_dbeaver.png


8. Diseñar un Diagrama Entidad-Relación (ERD)
1. Crea un nuevo esquema y diseña las tablas y relaciones en DBeaver.
2. Proyecto elegido: Plataforma de Cursos Online.
3. Entidades: usuarios, cursos, lecciones, evaluaciones, inscripciones, certificados.

- Imagen: ./imagenes/erd_diagrama.png

➡️ Ver la documentación completa de la Base de Datos aquí:
👉 ./base_de_datos.md


9. Subir Cambios a GitHub
- Fusiona la rama feature/database-setup con main:

git checkout main
git merge feature/database-setup
git push

- Imagen: ./imagenes/fusionar_ramas.png


🚀 Próximos Pasos
- Desarrollo del backend en PHP.
- Implementación de la API para la gestión de usuarios, cursos, evaluaciones, etc.
- Conexión del backend PHP con la base de datos PostgreSQL.
- Mejoras en la seguridad (autenticación y autorización).
- Despliegue de la plataforma en producción utilizando Docker Compose.


📂 Estructura de Carpetas Sugerida

proyecto/
├── backend/
│   ├── index.php
│   ├── api/
│   └── config/
├── documentacion/
│   ├── imagenes/
│   │   ├── crear_repositorio.png
│   │   ├── docker_compose.png
│   │   └── ...
│   ├── pasos.md
│   └── base_de_datos.md
├── docker-compose.yml
└── README.md


📝 Conclusión
El proyecto sigue buenas prácticas de desarrollo con Git, Docker y PostgreSQL. La estructura modular y el control de versiones permiten escalar el sistema y facilitar su mantenimiento.
Con el entorno Docker, el despliegue y la portabilidad del sistema son simples y rápidos.
