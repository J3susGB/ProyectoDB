# 📚 Documentación de la Base de Datos `ProyectoDB`

## ✅ Descripción General
Este documento describe el diseño e implementación de la base de datos relacional **ProyectoDB**, creada en **PostgreSQL**, orquestada en un contenedor **Docker** y administrada desde **DBeaver**.  
Se integra con un backend en **PHP** que accede a la base de datos para la gestión de usuarios, cursos, lecciones, evaluaciones e inscripciones.

---

## 📂 Estructura de la Base de Datos

### 🗂️ Esquema `public`
#### 📄 Tablas principales:
- `usuarios`
- `cursos`
- `lecciones`
- `evaluaciones`
- `inscripciones`
- `certificados`

---

### 🧩 Tablas y Atributos

#### `usuarios`
| Columna     | Tipo           | Clave         | Descripción                   |
|-------------|----------------|---------------|-------------------------------|
| id_usuario  | serial         | PK            | Identificador único del usuario |
| nombre      | varchar(100)   |               | Nombre del usuario           |
| correo      | varchar(100)   | Único         | Correo electrónico del usuario |
| contraseña  | varchar(255)   |               | Contraseña hasheada          |

#### `cursos`
| Columna       | Tipo          | Clave | Descripción                             |
|---------------|---------------|-------|-----------------------------------------|
| id_curso      | serial        | PK    | Identificador único del curso           |
| titulo        | varchar(100)  |       | Título del curso                       |
| descripcion   | text          |       | Descripción del curso                  |
| instructor_id | int4          | FK    | Llave foránea a `usuarios(id_usuario)` |

#### `lecciones`
| Columna      | Tipo          | Clave | Descripción                          |
|--------------|---------------|-------|--------------------------------------|
| id_leccion   | serial        | PK    | Identificador de la lección         |
| titulo       | varchar(100)  |       | Título de la lección                |
| contenido    | text          |       | Contenido detallado de la lección   |
| id_curso     | int4          | FK    | Llave foránea a `cursos(id_curso)`  |

#### `evaluaciones`
| Columna      | Tipo        | Clave | Descripción                          |
|--------------|-------------|-------|--------------------------------------|
| id_evaluacion| serial      | PK    | Identificador de la evaluación      |
| nombre       | varchar(100)|       | Nombre de la evaluación             |
| id_curso     | int4        | FK    | Llave foránea a `cursos(id_curso)`  |

#### `inscripciones`
| Columna     | Tipo   | Clave | Descripción                               |
|-------------|--------|-------|-------------------------------------------|
| id_usuario  | int4   | FK    | Llave foránea a `usuarios(id_usuario)`    |
| id_curso    | int4   | FK    | Llave foránea a `cursos(id_curso)`        |
| fecha       | date   |       | Fecha de la inscripción                  |

#### `certificados`
| Columna        | Tipo   | Clave | Descripción                              |
|----------------|--------|-------|------------------------------------------|
| id_certificado | serial | PK    | Identificador único del certificado      |
| id_usuario     | int4   | FK    | Llave foránea a `usuarios(id_usuario)`   |
| id_curso       | int4   | FK    | Llave foránea a `cursos(id_curso)`       |
| fecha_emision  | date   |       | Fecha de emisión del certificado         |

---

## 🔗 Relaciones de las Tablas
- `cursos.instructor_id` → `usuarios.id_usuario`
- `lecciones.id_curso` → `cursos.id_curso`
- `evaluaciones.id_curso` → `cursos.id_curso`
- `inscripciones.id_usuario` → `usuarios.id_usuario`
- `inscripciones.id_curso` → `cursos.id_curso`
- `certificados.id_usuario` → `usuarios.id_usuario`
- `certificados.id_curso` → `cursos.id_curso`

---

## ⚙️ Implementación Técnica

### 🔸 Motor de Base de Datos
- **PostgreSQL 15**
- Instalado y ejecutado en contenedor **Docker**.

### 🔸 Herramientas Adicionales
- **DBeaver** para diseño y administración del modelo ER.
- **PHP** para la lógica de negocio y la API que se comunica con la base de datos.

---

## 🔄 Flujo del Sistema

1. **Usuario final** accede al sistema a través de una **aplicación web (frontend)** que envía solicitudes HTTP al **backend en PHP**.
2. El **backend PHP** procesa las peticiones y realiza operaciones CRUD sobre la base de datos **PostgreSQL**:
   - Registra usuarios.
   - Inscribe alumnos en cursos.
   - Registra el avance en las lecciones.
   - Genera evaluaciones y calificaciones.
   - Emite certificados cuando se completan los cursos.
3. **PostgreSQL** almacena y gestiona toda la información persistente.
4. **DBeaver** se usa para administrar y monitorear la base de datos directamente (solo por los administradores del sistema).
5. Los cambios y datos generados por los usuarios se reflejan en tiempo real en la base de datos.
