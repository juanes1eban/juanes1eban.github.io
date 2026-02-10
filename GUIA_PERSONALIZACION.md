# Guía de Personalización del Curriculum

## Introducción

Este sitio web de curriculum vitae está construido con Jekyll y es fácil de personalizar. Todos los datos se gestionan a través de archivos YAML en la carpeta `_data/`.

## Archivos de Datos

### 1. Información Personal (_data/personal.yml)

Este archivo contiene tu información personal básica:

```yaml
nombre: Tu Nombre Completo
email: tu.email@ejemplo.com
telefono: "+34 XXX XXX XXX"
ubicacion: "Tu Ciudad, País"
linkedin: "https://linkedin.com/in/tu-usuario"
github: "https://github.com/tu-usuario"
resumen: >
  Breve descripción profesional sobre ti.
  Puedes escribir varias líneas aquí.
```

**Campos disponibles:**
- `nombre`: Tu nombre completo
- `email`: Tu dirección de correo electrónico
- `telefono`: Tu número de teléfono (opcional)
- `ubicacion`: Tu ciudad y país
- `linkedin`: URL de tu perfil de LinkedIn (opcional)
- `github`: URL de tu perfil de GitHub (opcional)
- `resumen`: Un breve resumen profesional sobre ti

### 2. Experiencia Profesional (_data/experience.yml)

Lista tus trabajos en orden cronológico inverso (más reciente primero):

```yaml
- puesto: "Título del Puesto"
  empresa: "Nombre de la Empresa"
  periodo: "Mes/Año - Mes/Año o Presente"
  ubicacion: "Ciudad, País"
  descripcion: "Descripción breve del puesto y responsabilidades"
  logros:
    - "Primer logro importante"
    - "Segundo logro importante"
    - "Tercer logro importante"

- puesto: "Otro Puesto"
  empresa: "Otra Empresa"
  # ... más campos
```

**Campos por trabajo:**
- `puesto`: Título de tu posición
- `empresa`: Nombre de la empresa
- `periodo`: Fechas de inicio y fin (usa "Presente" si sigues trabajando ahí)
- `ubicacion`: Ubicación de la empresa (opcional)
- `descripcion`: Descripción del puesto
- `logros`: Lista de logros y responsabilidades clave (opcional)

### 3. Educación (_data/education.yml)

Lista tu formación académica:

```yaml
- titulo: "Nombre del Título o Grado"
  institucion: "Nombre de la Universidad o Institución"
  periodo: "Año Inicio - Año Fin"
  descripcion: "Detalles adicionales sobre el programa (opcional)"

- titulo: "Otro Título"
  # ... más campos
```

**Campos por título:**
- `titulo`: Nombre del grado, máster, certificación, etc.
- `institucion`: Nombre de la universidad o institución
- `periodo`: Años de estudio
- `descripcion`: Información adicional (opcional)

### 4. Habilidades (_data/skills.yml)

Organiza tus habilidades por categorías:

```yaml
- categoria: "Lenguajes de Programación"
  items:
    - "JavaScript"
    - "Python"
    - "Java"

- categoria: "Frameworks"
  items:
    - "React"
    - "Django"
    - "Spring"

- categoria: "Herramientas"
  items:
    - "Git"
    - "Docker"
    - "AWS"
```

**Estructura:**
- `categoria`: Nombre de la categoría de habilidades
- `items`: Lista de habilidades dentro de esa categoría

## Personalizar Páginas

### Página de Inicio (index.md)

Edita `index.md` para cambiar el contenido de tu página principal. Puedes usar Markdown para formatear el texto.

### Página de CV (cv.md)

Edita `cv.md` para personalizar la introducción de tu curriculum. Los datos se cargan automáticamente desde los archivos YAML.

### Página de Contacto (contacto.md)

Edita `contacto.md` para personalizar tu página de contacto.

## Personalizar Estilos

Los estilos están en la carpeta `_sass/`:

- `_base.scss`: Estilos base generales
- `_layout.scss`: Estilos de la estructura del sitio
- `_resume.scss`: Estilos específicos del curriculum

Para cambiar colores, fuentes u otros aspectos visuales, edita estos archivos.

### Colores principales

En `_sass/_base.scss` y `_sass/_layout.scss` encontrarás los colores principales:
- `#2c3e50`: Color del encabezado y títulos
- `#3498db`: Color de enlaces y acentos
- `#34495e`: Color del pie de página

## Desplegar en GitHub Pages

1. Asegúrate de que tu repositorio se llame `tu-usuario.github.io`
2. Los cambios se desplegarán automáticamente cuando hagas push a la rama `main`
3. Tu sitio estará disponible en `https://tu-usuario.github.io`

## Configuración Avanzada

### Cambiar el Título del Sitio

Edita `_config.yml`:

```yaml
title: Tu Nombre
email: tu@email.com
description: Tu descripción personalizada
```

### Añadir Nuevas Secciones

Para añadir nuevas secciones a tu CV:

1. Crea un nuevo archivo YAML en `_data/`
2. Edita `_layouts/resume.html` para incluir la nueva sección
3. Sigue el patrón de las secciones existentes

## Construcción Local

Para ver tu sitio localmente antes de publicarlo:

```bash
# Instalar dependencias (primera vez)
bundle install

# Construir y servir el sitio
bundle exec jekyll serve

# Visitar http://localhost:4000
```

## Consejos

- Mantén las descripciones concisas y enfocadas en resultados
- Usa verbos de acción en tus logros
- Actualiza regularmente tu información
- Revisa la ortografía y gramática
- Personaliza los colores para que reflejen tu marca personal

## Soporte

Para más información sobre Jekyll, visita:
- [Documentación de Jekyll](https://jekyllrb.com/docs/)
- [GitHub Pages](https://pages.github.com/)

---

¡Buena suerte con tu curriculum vitae!
