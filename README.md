# Juan Esteban Valenzuela Rodriguez - Curriculum Vitae

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-success)](https://smellwing.github.io/juan-valenzuela-rodriguez.github.io/)
[![Jekyll](https://img.shields.io/badge/Jekyll-4.x-red)](https://jekyllrb.com/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/juanestebanvalenzuela/)

## 🎯 Sobre Mi

Sitio web personal de curriculum vitae desplegado en GitHub Pages con **Jekyll** como generador de sitios estáticos.

**Ingeniero Civil en Computacion** con más de 15 años de experiencia en desarrollo full-stack. Especializado en .NET, JavaScript, PHP, Azure y metodologías ágiles.

## 🚀 Sitio en Vivo

Visita mi CV en: **[https://smellwing.github.io/juan-valenzuela-rodriguez.github.io/](https://smellwing.github.io/juan-valenzuela-rodriguez.github.io/)**

## 🏗️ Arquitectura Jekyll

Este proyecto utiliza Jekyll con una **arquitectura modular y profesional**:

### 📁 Estructura del Proyecto

```
juan-valenzuela-rodriguez.github.io/
├── _config.yml                 # Configuración global de Jekyll
├── index.md                    # Página principal en Markdown
├── sitemap.xml                 # Mapa del sitio para SEO
├── robots.txt                  # Configuración para motores de búsqueda
├── .gitignore                  # Archivos ignorados por Git
│
├── _data/                      # 📊 Datos estructurados en YAML
│   ├── personal.yml           # Información personal y bio
│   ├── experiences.yml        # Historial laboral
│   ├── skills.yml             # Habilidades técnicas
│   ├── projects.yml           # Proyectos destacados
│   ├── education.yml          # Formación académica
│   ├── certifications.yml     # Certificaciones
│   ├── references.yml         # Referencias profesionales
│   └── volunteering.yml       # Voluntariado
│
├── _layouts/                   # 📄 Plantillas HTML
│   └── default.html           # Layout base del sitio
│
├── _includes/                  # 🧩 Componentes reutilizables
│   ├── header.html            # Cabecera del sitio
│   ├── footer.html            # Pie de página
│   ├── structured-data.html   # JSON-LD para SEO
│   ├── experience-card.html   # Card de experiencia
│   ├── skill-category.html    # Categoría de habilidades
│   └── project-card.html      # Card de proyecto
│
├── assets/                     # 🎨 Recursos estáticos
│   └── css/
│       ├── base.css           # Estilos base y variables
│       ├── header-footer.css  # Estilos de header/footer
│       ├── sections.css       # Estilos de secciones
│       ├── experiences.css    # Estilos de experiencias
│       ├── skills.css         # Estilos de habilidades
│       ├── projects.css       # Estilos de proyectos
│       ├── misc.css           # Estilos misceláneos
│       └── responsive.css     # Media queries
│
└── .github/workflows/
    └── jekyll-gh-pages.yml    # GitHub Actions para CI/CD
```

## 🎨 Ventajas de esta Arquitectura

### ✅ **Separación de Contenido y Presentación**
- **Datos en YAML:** Todos los datos están centralizados en `_data/`
- **Estilos en CSS:** Cada componente tiene su propio archivo CSS
- **Contenido en Markdown:** Fácil de editar sin tocar HTML

### ✅ **Componentes Reutilizables**
```liquid
{% include experience-card.html experience=experience %}
{% include skill-category.html category=category %}
```

### ✅ **Actualización Centralizada**
- Cambias tus datos en `_data/personal.yml`
- Se actualiza automáticamente en TODO el sitio
- Sin duplicación de código

### ✅ **Mantenimiento Simplificado**
```yaml
# Para agregar una nueva experiencia:
# Edita _data/experiences.yml y agrega:
- role: "Nuevo Cargo"
  company: "Nueva Empresa"
  highlights:
    - "Logro 1"
    - "Logro 2"
```

## 🛠️ Stack Tecnológico

- **Backend:** .NET 8, .NET 6, C#, NodeJS, Express, PHP, Laravel
- **Frontend:** Angular, JavaScript, TypeScript, HTML5, CSS3
- **Cloud:** Azure (Blobs, Logic Apps, Web Apps), AWS (EC2, S3)
- **DevOps:** Azure DevOps, Git, CI/CD Pipelines, OpenShift
- **Databases:** SQL Server, MongoDB, PostgreSQL
- **BI & ETL:** Pentaho, Tableau, SSDT
- **AI Tools:** Windsurf IDE, GitHub Copilot, Claude AI, ChatGPT
- **Generador:** Jekyll 4.x

## 📝 Guía de Uso

### Actualizar Información Personal
Edita `_data/personal.yml`:
```yaml
name: "Tu Nombre"
email: "tu@email.com"
bio: "Tu biografía..."
```

### Agregar Nueva Experiencia
Edita `_data/experiences.yml`:
```yaml
- role: "Nuevo Cargo"
  company: "Empresa"
  start_date: "2026-01"
  current: true
  highlights:
    - "Logro importante"
```

### Agregar Nueva Habilidad
Edita `_data/skills.yml`:
```yaml
categories:
  - name: "Nueva Categoría"
    skills:
      - "Skill 1"
      - "Skill 2"
```

### Modificar Estilos
- Edita archivos en `assets/css/`
- Variables en `assets/css/base.css`:
```css
:root {
    --primary-color: #0077b5;
    --secondary-color: #00a0dc;
}
```

## 🚀 Desarrollo Local

### Requisitos
- Ruby 2.7+
- Bundler
- Jekyll 4.x

### Instalación
```bash
# Instalar dependencias
bundle install

# Ejecutar servidor local
bundle exec jekyll serve

# Visitar: http://localhost:4000/juan-valenzuela-rodriguez.github.io/
```

### Sin Ruby (usando Docker)
```bash
docker run -p 4000:4000 -v $(pwd):/site bretfisher/jekyll-serve
```

## 📦 Deployment

El sitio se despliega automáticamente mediante GitHub Actions:

1. Push a la rama `main`
2. GitHub Actions ejecuta Jekyll build
3. Deploy a GitHub Pages
4. Sitio actualizado en 2-3 minutos

```bash
git add .
git commit -m "update: Actualización de CV"
git push origin main
```

## 🎯 Características

- ✅ **Arquitectura Modular** - Separación clara de datos, lógica y presentación
- ✅ **YAML Data Files** - Datos estructurados y fáciles de editar
- ✅ **Componentes Reutilizables** - Includes de Jekyll para DRY
- ✅ **CSS Modular** - Archivos CSS separados por componente
- ✅ **SEO Optimizado** - Meta tags, Open Graph, JSON-LD
- ✅ **Responsive Design** - Adaptado para todos los dispositivos
- ✅ **GitHub Actions** - CI/CD automático
- ✅ **Markdown** - Contenido fácil de editar

## 📊 Datos Estructurados

El sitio genera automáticamente JSON-LD con:
- Perfil personal completo
- Experiencia laboral (8 posiciones)
- Habilidades técnicas (8 categorías)
- Certificaciones y cursos
- Proyectos y contribuciones Git

## 🔜 Mejoras Futuras

- [ ] Blog con posts en `_posts/`
- [ ] Portfolio visual de proyectos
- [ ] Versión en inglés (i18n)
- [ ] Modo oscuro
- [ ] Galería de imágenes
- [ ] Sección de testimonios
- [ ] Dominio personalizado

## 📝 Licencia

© 2026 Juan Esteban Valenzuela Rodriguez. Todos los derechos reservados.

## 📧 Contacto

- **Email:** juan.esteban.valenzuela@gmail.com
- **LinkedIn:** [linkedin.com/in/juanestebanvalenzuela](https://www.linkedin.com/in/juanestebanvalenzuela/)
- **GitHub:** [github.com/juan-valenzuela-rodriguez](https://github.com/juan-valenzuela-rodriguez)
- **Teléfono:** +56 9 98115373
- **Ubicación:** Santiago, Chile

---

**Última actualización:** Febrero 2026 | **Migrado a Jekyll con arquitectura modular**
