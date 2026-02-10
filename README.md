# Juan Valenzuela Rodriguez - Curriculum Vitae

Sitio personal con curriculum vitae construido con Jekyll.

## Estructura del Proyecto

Este sitio utiliza Jekyll para generar un curriculum vitae profesional y personalizable.

### Estructura de Archivos

```
.
├── _config.yml           # Configuración de Jekyll
├── _data/                # Datos del CV en formato YAML
│   ├── personal.yml      # Información personal
│   ├── experience.yml    # Experiencia profesional
│   ├── education.yml     # Educación y formación
│   └── skills.yml        # Habilidades técnicas
├── _layouts/             # Plantillas de diseño
│   ├── default.html      # Plantilla base
│   └── resume.html       # Plantilla para el CV
├── _sass/                # Estilos SCSS
│   ├── _base.scss        # Estilos base
│   ├── _layout.scss      # Estilos de layout
│   └── _resume.scss      # Estilos específicos del CV
├── assets/
│   └── css/
│       └── main.scss     # Archivo principal de estilos
├── index.md              # Página de inicio
├── cv.md                 # Página del curriculum
├── contacto.md           # Página de contacto
├── Gemfile               # Dependencias de Ruby
└── README.md             # Este archivo
```

## Instalación y Uso

### Prerrequisitos

- Ruby (versión 2.7 o superior)
- Bundler

### Instalación Local

1. Clonar el repositorio:
```bash
git clone https://github.com/smellwing/juan-valenzuela-rodriguez.github.io.git
cd juan-valenzuela-rodriguez.github.io
```

2. Instalar las dependencias:
```bash
bundle install
```

3. Ejecutar Jekyll localmente:
```bash
bundle exec jekyll serve
```

4. Abrir en el navegador:
```
http://localhost:4000
```

## Personalización

### Modificar Información Personal

Edita el archivo `_data/personal.yml` con tu información:

```yaml
nombre: Tu Nombre
email: tu@email.com
telefono: "+34 XXX XXX XXX"
ubicacion: "Tu Ciudad, País"
linkedin: "https://linkedin.com/in/tu-perfil"
github: "https://github.com/tu-usuario"
```

### Añadir Experiencia Profesional

Edita `_data/experience.yml` para añadir tus trabajos:

```yaml
- puesto: "Tu Puesto"
  empresa: "Nombre de la Empresa"
  periodo: "YYYY - YYYY"
  ubicacion: "Ciudad, País"
  descripcion: "Descripción del puesto"
  logros:
    - "Logro 1"
    - "Logro 2"
```

### Añadir Educación

Edita `_data/education.yml`:

```yaml
- titulo: "Título Académico"
  institucion: "Universidad o Institución"
  periodo: "YYYY - YYYY"
  descripcion: "Descripción opcional"
```

### Añadir Habilidades

Edita `_data/skills.yml`:

```yaml
- categoria: "Categoría de Habilidad"
  items:
    - "Habilidad 1"
    - "Habilidad 2"
```

## Despliegue en GitHub Pages

Este sitio está configurado para desplegarse automáticamente en GitHub Pages:

1. Asegúrate de que el repositorio se llama `tu-usuario.github.io`
2. Ve a Settings → Pages en tu repositorio
3. Selecciona la rama `main` como fuente
4. GitHub Pages construirá y publicará automáticamente tu sitio

Tu sitio estará disponible en: `https://tu-usuario.github.io`

## Características

- ✅ Diseño responsive y profesional
- ✅ Fácil personalización mediante archivos YAML
- ✅ Estilos modernos y limpios
- ✅ Optimizado para impresión (PDF)
- ✅ Navegación sencilla
- ✅ SEO optimizado

## Tecnologías Utilizadas

- **Jekyll 4.3**: Generador de sitios estáticos
- **SCSS**: Preprocesador CSS
- **YAML**: Formato de datos para el contenido
- **Markdown**: Formato para las páginas

## Licencia

Este proyecto es de código abierto y está disponible para uso personal y profesional.

## Contacto

Para más información, visita el sitio web o contacta a través de los medios indicados en la página de contacto.
