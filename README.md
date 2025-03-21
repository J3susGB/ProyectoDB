# ProyectoDB 📦🐘
### *Jesús Gómez - Desarrollador Aplicaciones Web⚡*
[![Contact Me](https://img.shields.io/badge/Email-informational?style=for-the-badge&logo=Mail.Ru&logoColor=fff&color=c6362c)](mailto:jgomezbeltran88@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-informational?style=for-the-badge&logo=linkedin&logoColor=fff&color=0274b3)](https://www.linkedin.com/in/jesusgb-dev/)
[![Linktree](https://img.shields.io/badge/-Linktree-323330?style=for-the-badge&logo=linktree&logoColor=1de9b6)](https://linktr.ee/jesusgb?utm_source=linktree_admin_share)

## Descripción 📄

Este es un proyecto de práctica para aprender a gestionar un repositorio en **GitHub**, trabajar con **Docker** para levantar un contenedor de **PostgreSQL**, y diseñar un **Diagrama Entidad-Relación (ERD)**.  
La base de datos está pensada para una **Tienda de Ropa**, pero puedes adaptarla fácilmente a cualquier otro negocio o necesidad.

---

## Objetivos 🎯

- Crear y gestionar un repositorio en **GitHub**.
- Trabajar con ramas, commits, y realizar rollback de cambios en **Git**.
- Configurar y levantar un contenedor de **PostgreSQL** usando **Docker Compose**.
- Conectarse a la base de datos desde **DBeaver**.
- Diseñar un **Diagrama Entidad-Relación (ERD)** para el proyecto.
- Documentar el proceso paso a paso.

---

## Estructura del Proyecto 📁

```
ProyectoDB/
│
├── README.md
├── docker-compose.yml
└── documentación/
    ├── erd.png
    └── pasos.md
```

---

## Requisitos previos 🛠️

- Tener instalado **Docker** y **Docker Compose**.
- Tener instalado **Git**.
- Tener instalado un gestor de bases de datos como **DBeaver** (opcional pero recomendado).

---

## Paso a Paso 📝

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/ProyectoDB.git
cd ProyectoDB
```

---

### 2. Configurar Docker Compose

Creamos el archivo `docker-compose.yml` con el siguiente contenido:

```yaml
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
```

---

### 3. Levantar el contenedor de PostgreSQL

```bash
docker-compose up -d
```

Verifica que el contenedor está corriendo:

```bash
docker ps
```

---

### 4. Crear ramas y realizar commits

```bash
git checkout -b feature/database-setup
```

Una vez hechos los cambios necesarios:

```bash
git add .
git commit -m "feat(database): add PostgreSQL setup with Docker Compose"
git push -u origin feature/database-setup
```

---

### 5. Practicar rollback y corrección de errores

#### Deshacer el último commit (sin perder los cambios):

```bash
git reset --soft HEAD~1
```

#### Volver a un commit anterior:

```bash
git checkout <ID-del-commit>
```

#### Revertir un commit sin perder el historial:

```bash
git revert <ID-del-commit>
```

#### Eliminar una rama remota:

```bash
git push origin --delete nombre-rama
```

---

### 6. Conectarse a PostgreSQL con DBeaver

- **Host:** localhost  
- **Puerto:** 5432  
- **Base de datos:** proyectodb  
- **Usuario:** user  
- **Contraseña:** password  

Haz clic en **Test Connection** para verificar que funciona correctamente.

---

### 7. Diagrama Entidad-Relación (ERD)

Aquí diseñamos el modelo de la base de datos para la **Tienda de Ropa**, que incluye:

- Productos  
- Categorías  
- Clientes  
- Pedidos  
- Detalles de Pedido  
- Facturas  

📌 _Falta agregar imagen_  
Ejemplo:  
![ERD](documentación/erd.png)

---

### 8. Subir cambios a `main`

```bash
git checkout main
git merge feature/database-setup
git push
```

---

## Documentación 🗂️

En la carpeta `documentación/` encontrarás el archivo `pasos.md` que explica cada paso con más detalle y capturas de pantalla.

---

## Tecnologías utilizadas ⚙️

- PostgreSQL
- Docker / Docker Compose
- Git / GitHub
- DBeaver
- Markdown

---

## Estado del Proyecto 🚀

✅ Proyecto terminado y funcional.  
📌 Si encuentras algún error o tienes sugerencias, no dudes en abrir un issue o realizar un pull request.

---

## Autor ✍️

- **Tu Nombre**  
GitHub: [J3susGB](https://github.com/J3susGB)

---

### *Hecho con ❤️ por Jesús Gómez Freelancer Web Developer⚡*
