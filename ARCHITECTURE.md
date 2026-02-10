# 🎨 Guía de Arquitectura Jekyll

## 🏗️ Filosofía de Diseño

Este proyecto utiliza una **arquitectura Jekyll modular y profesional** que separa claramente:

1. **Datos** (YAML files en `_data/`)
2. **Presentación** (Layouts en `_layouts/`)
3. **Componentes** (Includes en `_includes/`)
4. **Estilos** (CSS modular en `assets/css/`)
5. **Contenido** (Markdown en la raíz)

---

## 📊 1. Data Files (`_data/`)

### ¿Por qué YAML?
- Más fácil de leer y editar que HTML
- Sin duplicación de código
- Cambios centralizados

### Estructura de Datos

#### `personal.yml` - Información personal
```yaml
name: "Juan Esteban Valenzuela Rodriguez"
job_title: "Ingeniero Civil en Computacion"
email: "juan.esteban.valenzuela@gmail.com"
bio: "Tu biografía..."
```

**Uso en templates:**
```liquid
{{ site.data.personal.name }}
{{ site.data.personal.email }}
```

#### `experiences.yml` - Historial laboral
```yaml
- role: "Ingeniero Civil - Lider Tecnico"
  company: "SAG"
  start_date: "2019-09"
  current: true
  highlights:
    - "Logro 1"
    - "Logro 2"
```

**Uso en templates:**
```liquid
{% for exp in site.data.experiences %}
  {{ exp.role }} - {{ exp.company }}
{% endfor %}
```

#### `skills.yml` - Habilidades por categorías
```yaml
categories:
  - name: "Backend Development"
    skills:
      - ".NET 8"
      - "NodeJS"
```

**Uso en templates:**
```liquid
{% for category in site.data.skills.categories %}
  <h3>{{ category.name }}</h3>
  {% for skill in category.skills %}
    <span>{{ skill }}</span>
  {% endfor %}
{% endfor %}
```

---

## 📄 2. Layouts (`_layouts/`)

### `default.html` - Layout base

**Estructura:**
```html
<!DOCTYPE html>
<html>
<head>
  <!-- Meta tags dinámicos -->
  <title>{{ page.title }} - {{ site.title }}</title>
  <!-- CSS -->
  <link rel="stylesheet" href="{{ '/assets/css/base.css' | relative_url }}">
</head>
<body>
  {% include header.html %}
  {{ content }}  <!-- Aquí se inserta el contenido de cada página -->
  {% include footer.html %}
</body>
</html>
```

**Variables disponibles:**
- `page.title` - Título de la página actual
- `page.description` - Descripción de la página
- `site.*` - Variables de `_config.yml`
- `content` - Contenido de la página que usa este layout

---

## 🧩 3. Includes (`_includes/`)

### Componentes Reutilizables

#### `header.html` - Cabecera del sitio
```liquid
<header>
  <h1>{{ site.data.personal.name }}</h1>
  <p>{{ site.data.personal.job_title }}</p>
</header>
```

#### `experience-card.html` - Card de experiencia
```liquid
<!-- Uso: {% include experience-card.html experience=exp %} -->
<div class="experience-item">
  <h3>{{ include.experience.role }}</h3>
  <p>{{ include.experience.company }}</p>
  <ul>
    {% for highlight in include.experience.highlights %}
      <li>{{ highlight }}</li>
    {% endfor %}
  </ul>
</div>
```

**Parámetros:**
- `include.experience` - Objeto de experiencia pasado al include

#### `skill-category.html` - Categoría de habilidades
```liquid
<!-- Uso: {% include skill-category.html category=cat %} -->
<div class="skill-category">
  <h3>{{ include.category.name }}</h3>
  <div class="skill-tags">
    {% for skill in include.category.skills %}
      <span class="skill-tag">{{ skill }}</span>
    {% endfor %}
  </div>
</div>
```

---

## 🎨 4. CSS Modular (`assets/css/`)

### Estructura de Archivos

```
assets/css/
├── base.css           → Variables CSS, reset, estilos globales
├── header-footer.css  → Estilos de header y footer
├── sections.css       → Estilos de sections
├── experiences.css    → Estilos de tarjetas de experiencia
├── skills.css         → Estilos de habilidades
├── projects.css       → Estilos de proyectos
├── misc.css           → Estilos misceláneos
└── responsive.css     → Media queries
```

### `base.css` - Variables CSS
```css
:root {
    --primary-color: #0077b5;
    --secondary-color: #00a0dc;
    --text-color: #333;
    --bg-color: #f3f6f8;
    --card-bg: #ffffff;
}
```

**Ventajas:**
- Cambias el color una vez, se actualiza en todo el sitio
- Fácil mantenimiento
- Posibilidad de crear temas

### Carga de CSS en `default.html`
```html
<link rel="stylesheet" href="{{ '/assets/css/base.css' | relative_url }}">
<link rel="stylesheet" href="{{ '/assets/css/header-footer.css' | relative_url }}">
<!-- etc -->
```

---

## 📝 5. Contenido en Markdown

### `index.md` - Página principal

```markdown
---
layout: default
title: "Curriculum Vitae"
description: "Ingeniero Civil..."
---

<section id="about">
    <h2>Acerca de Mi</h2>
    <p>{{ site.data.personal.bio }}</p>
</section>

<section id="experience">
    <h2>Experiencia Laboral</h2>
    {% for exp in site.data.experiences %}
        {% include experience-card.html experience=exp %}
    {% endfor %}
</section>
```

**Front Matter (YAML):**
- `layout` - Qué layout usar
- `title` - Título de la página
- `description` - Descripción para SEO

**Contenido:**
- Puede mezclar HTML y Liquid
- Acceso a datos con `site.data.*`
- Uso de includes con `{% include %}`

---

## 🔄 Flujo de Generación

```
1. Jekyll lee _config.yml
   ↓
2. Carga datos de _data/*.yml
   ↓
3. Lee index.md
   ↓
4. Procesa Liquid templates {{ }} {% %}
   ↓
5. Aplica layout default.html
   ↓
6. Incluye componentes de _includes/
   ↓
7. Genera HTML final en _site/
   ↓
8. GitHub Pages sirve el sitio
```

---

## 💡 Casos de Uso Comunes

### Agregar nueva experiencia
1. Edita `_data/experiences.yml`
2. Agrega nuevo objeto YAML
3. Push a GitHub
4. ✅ Automáticamente aparece en el sitio

### Cambiar colores del sitio
1. Edita `assets/css/base.css`
2. Modifica variables CSS en `:root`
3. Push a GitHub
4. ✅ Colores actualizados en todo el sitio

### Agregar nueva sección
1. Crea include en `_includes/nueva-seccion.html`
2. Crea datos en `_data/nueva-seccion.yml`
3. Agrega en `index.md`:
```liquid
<section id="nueva">
    <h2>Nueva Sección</h2>
    {% include nueva-seccion.html %}
</section>
```

### Modificar header/footer
1. Edita `_includes/header.html` o `footer.html`
2. Cambios se reflejan en todas las páginas
3. ✅ Sin tocar múltiples archivos

---

## 🎯 Ventajas de esta Arquitectura

### ✅ **DRY (Don't Repeat Yourself)**
- Código reutilizable
- Sin duplicación
- Cambios centralizados

### ✅ **Mantenibilidad**
- Estructura clara
- Fácil de entender
- Cada archivo tiene un propósito

### ✅ **Escalabilidad**
- Fácil agregar nuevas secciones
- Fácil agregar nuevos datos
- Fácil modificar estilos

### ✅ **Separación de Responsabilidades**
- Datos ≠ Presentación ≠ Estilos
- Editores pueden cambiar datos sin tocar HTML
- Diseñadores pueden cambiar CSS sin tocar datos

---

## 📚 Recursos de Jekyll

- **Liquid Syntax:** https://shopify.github.io/liquid/
- **Jekyll Docs:** https://jekyllrb.com/docs/
- **Data Files:** https://jekyllrb.com/docs/datafiles/
- **Includes:** https://jekyllrb.com/docs/includes/
- **Layouts:** https://jekyllrb.com/docs
/layouts/

---

## 🚀 Próximos Pasos

1. **Blog:** Agregar carpeta `_posts/` para artículos
2. **Collections:** Crear `_projects/` para portfolio
3. **i18n:** Soporte multi-idioma
4. **Temas:** Permitir cambio de tema
5. **Plugins:** Agregar más funcionalidad

---

**¿Preguntas?** Consulta el README.md principal o la documentación de Jekyll.
