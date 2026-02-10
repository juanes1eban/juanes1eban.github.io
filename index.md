---
layout: default
title: Inicio
---

# Bienvenido a mi Sitio Personal

Hola, soy **{{ site.data.personal.nombre }}**, {{ site.data.personal.resumen }}

## Sobre Mí

Este es mi sitio personal donde comparto mi experiencia profesional, habilidades y proyectos.

### ¿Qué encontrarás aquí?

- **[Curriculum Vitae](/cv)**: Mi experiencia profesional, educación y habilidades
- **Contacto**: Información para ponerte en contacto conmigo

### Contacto Rápido

{% if site.data.personal.email %}
📧 **Email**: [{{ site.data.personal.email }}](mailto:{{ site.data.personal.email }})
{% endif %}

{% if site.data.personal.linkedin %}
💼 **LinkedIn**: [Ver perfil]({{ site.data.personal.linkedin }})
{% endif %}

{% if site.data.personal.github %}
💻 **GitHub**: [Ver perfil]({{ site.data.personal.github }})
{% endif %}

---

*Última actualización: {{ 'now' | date: "%B %Y" }}*
