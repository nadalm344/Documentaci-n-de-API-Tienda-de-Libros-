# 📚 API de Gestión de Libros (BookStore API)

Esta documentación describe cómo interactuar con la API de BookStore para gestionar el inventario de libros de forma técnica y eficiente.

---

## 🚀 Introducción
La API de BookStore permite a los desarrolladores consultar, agregar y editar libros en la base de datos. Está diseñada bajo la arquitectura **REST**.

## 🛠️ Autenticación
Para realizar peticiones, es necesario incluir una "API Key" en la cabecera (header) de cada solicitud:
`Authorization: Bearer TU_TOKEN_AQUÍ`

---

## 📖 Puntos de Acceso (Endpoints)

### 1. Obtener todos los libros
Muestra la lista completa de libros disponibles.

* **URL:** `/api/v1/books`
* **Método:** `GET`
* **Respuesta Exitosa (200 OK):**

| Campo | Tipo | Descripción |
| :--- | :--- | :--- |
| `id` | Integer | Identificador único del libro. |
| `titulo` | String | Nombre completo de la obra. |
| `autor` | String | Escritor del libro. |

---

### 2. Agregar un nuevo libro
Permite registrar un libro nuevo en el sistema.

* **URL:** `/api/v1/books`
* **Método:** `POST`
* **Cuerpo de la petición (JSON):**

```json
{
  "titulo": "Cien años de soledad",
  "autor": "Gabriel García Márquez",
  "precio": 25.50
}  > [!CAUTION]
> **401 Unauthorized:** El token de seguridad no es válido o expiró.
> 
> **404 Not Found:** El libro solicitado no existe en la base de datos.
