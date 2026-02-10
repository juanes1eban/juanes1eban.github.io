---
layout: default
title: Contacto
---

# Contacto

¿Interesado en colaborar o tienes alguna pregunta? ¡Me encantaría saber de ti!

## Información de Contacto

{% if site.data.personal.email %}
### Email
📧 [{{ site.data.personal.email }}](mailto:{{ site.data.personal.email }})
{% endif %}

{% if site.data.personal.telefono %}
### Teléfono
📱 {{ site.data.personal.telefono }}
{% endif %}

{% if site.data.personal.ubicacion %}
### Ubicación
📍 {{ site.data.personal.ubicacion }}
{% endif %}

## Redes Sociales

{% if site.data.personal.linkedin %}
**LinkedIn**: [{{ site.data.personal.nombre }}]({{ site.data.personal.linkedin }})
{% endif %}

{% if site.data.personal.github %}
**GitHub**: [Ver perfil]({{ site.data.personal.github }})
{% endif %}

---

*Respondo normalmente en 24-48 horas*
