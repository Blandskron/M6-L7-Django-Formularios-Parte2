# Django Form Handling Project - Parte 2

Esta es la continuación del proyecto original, donde hemos mejorado la presentación y funcionalidad utilizando **Bootstrap** para el diseño y adoptando una estructura de plantillas base para mantener la consistencia en toda la aplicación.

## Cambios Realizados

### 1. **Integración de Bootstrap**
Se ha agregado **Bootstrap 5** para mejorar la apariencia de los formularios y las páginas en general:
- Se incluyó el enlace al CDN de Bootstrap en el archivo `base.html`.
- Se estilizaron los campos del formulario utilizando los widgets de Django (`form-control` y `form-select`).

### 2. **Uso de un Archivo Base (`base.html`)**
Se creó un archivo `base.html` que sirve como plantilla base para todas las páginas de la aplicación. Este incluye:
- Navegación global con enlaces a las secciones de autores y libros.
- Contenedor principal con bloques `{% block title %}` y `{% block content %}` para personalizar el contenido de cada página.

### 3. **Refactorización de Plantillas**
Las plantillas individuales (`author_form.html`, `author_list.html`, `book_form.html`, `book_list.html`) ahora extienden `base.html` utilizando `{% extends "base.html" %}`. Esto asegura:
- Consistencia en el diseño.
- Código más limpio y reutilizable.

### 4. **Estilización de Formulario**
Los formularios (`AuthorForm` y `BookForm`) ahora tienen clases de Bootstrap directamente aplicadas a sus campos mediante los widgets en la clase `Meta`.

## Estructura de Archivos

- **`base.html`**: Plantilla base que incluye el diseño principal y la barra de navegación.
- Plantillas específicas:
  - **`author_form.html`**: Formulario para crear autores.
  - **`author_list.html`**: Lista de autores.
  - **`book_form.html`**: Formulario para crear libros.
  - **`book_list.html`**: Lista de libros.
- Formularios (`forms.py`):
  - `AuthorForm` y `BookForm` estilizados con clases de Bootstrap.

## Instalación y Configuración

Si ya tienes el proyecto original configurado, solo necesitas:
1. Asegurarte de que Bootstrap está accesible a través de su CDN. No requiere instalación adicional.
2. Actualizar las plantillas y el archivo `forms.py` con los cambios realizados en esta parte.

### Nuevas Rutas de Navegación
La barra de navegación global incluye enlaces a:
- `/authors/`: Lista de autores.
- `/authors/new/`: Formulario para crear autores.
- `/books/`: Lista de libros.
- `/books/new/`: Formulario para crear libros.

## Cómo Probar los Cambios

1. Ejecuta el servidor de desarrollo:
   ```bash
   python manage.py runserver
   ```

2. Abre el navegador y accede a las URLs:
   - [http://127.0.0.1:8000/authors/](http://127.0.0.1:8000/authors/)
   - [http://127.0.0.1:8000/books/](http://127.0.0.1:8000/books/)

3. Verifica que:
   - Los formularios se muestran con estilos de Bootstrap.
   - Las páginas tienen un diseño consistente gracias a `base.html`.
