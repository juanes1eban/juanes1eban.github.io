# ⚡ Quick Start Guide

Guía rápida para empezar a trabajar con el sitio Jekyll.

---

## 🚀 Publicar Cambios (Lo Más Común)

```bash
# 1. Hacer cambios en archivos YAML o CSS
code _data/experiences.yml

# 2. Agregar, commitear y publicar
git add .
git commit -m "update: Descripción de tus cambios"
git push origin main

# 3. Esperar 2-3 minutos
# GitHub Actions compila y despliega automáticamente
```

**URL del sitio:** https://smellwing.github.io/juan-valenzuela-rodriguez.github.io/

---

## 📝 Ediciones Comunes

### Actualizar teléfono/email

```bash
code _data/personal.yml
```

### Agregar nueva experiencia laboral

```bash
code _data/experiences.yml
# Agregar al inicio del archivo
```

### Agregar nueva habilidad

```bash
code _data/skills.yml
# Agregar en la categoría correspondiente
```

### Agregar certificación

```bash
code _data/certifications.yml
```

### Cambiar colores del sitio

```bash
code assets/css/base.css
# Editar variables CSS en :root
```

---

## 🎨 Personalización Básica

### Cambiar color primario

[assets/css/base.css](assets/css/base.css):
```css
:root {
    --primary-color: #0077b5;  ← Cambia aquí
}
```

### Modificar header

```bash
code _includes/header.html
```

### Modificar footer

```bash
code _includes/footer.html
```

---

## 🧪 Testear Localmente (Opcional)

### Opción 1: Con Docker (Recomendado)
```bash
docker run --rm -v ${PWD}:/srv/jekyll -p 4000:4000 jekyll/jekyll jekyll serve
```

### Opción 2: Jekyll Local
```bash
bundle exec jekyll serve --baseurl '/juan-valenzuela-rodriguez.github.io'
# Visita: http://localhost:4000/juan-valenzuela-rodriguez.github.io/
```

---

## 📁 Estructura Rápida

```
_data/          ← Edita tus datos aquí (YAML)
_includes/      ← Componentes reutilizables
_layouts/       ← Plantillas HTML
assets/css/     ← Estilos CSS modulares
index.md        ← Contenido principal
_config.yml     ← Configuración Jekyll
```

---

## ⚙️ Comandos Git Útiles

```bash
# Ver estado
git status

# Ver cambios
git diff

# Deshacer cambios no guardados
git checkout -- archivo.yml

# Ver historial
git log --oneline

# Crear rama de prueba
git checkout -b mi-prueba
```

---

## 🔍 Verificar Deployment

1. **Push a GitHub:**
   ```bash
   git push origin main
   ```

2. **Ver progreso:**
   - Ve a: https://github.com/smellwing/juan-valenzuela-rodriguez.github.io/actions
   - Espera el checkmark verde ✅

3. **Visitar sitio:**
   - https://smellwing.github.io/juan-valenzuela-rodriguez.github.io/

---

## 🆘 Problemas Comunes

### Sitio no se actualiza

```bash
# Forzar rebuild
git commit --allow-empty -m "trigger rebuild"
git push origin main
```

### Error de sintaxis YAML

- Verifica indentación (2 espacios)
- Strings con `:` deben ir entre comillas: `"Texto: con dos puntos"`
- Arrays usan `-` con espacios después

### CSS no se aplica

- Verifica que el archivo CSS esté en `assets/css/`
- Verifica que esté linkeado en `_layouts/default.html`
- Limpia cache del navegador (Ctrl+Shift+R)

---

## 📚 Más Información

- **Guía completa:** [README.md](README.md)
- **Arquitectura:** [ARCHITECTURE.md](ARCHITECTURE.md)
- **Deployment:** [DEPLOYMENT.md](DEPLOYMENT.md)
- **Migración:** [JEKYLL_MIGRATION.md](JEKYLL_MIGRATION.md)

---

## 💡 Workflow Recomendado

```
1. Editar → _data/*.yml o assets/css/*.css
2. Test local (opcional) → bundle exec jekyll serve
3. Commit → git commit -m "mensaje"
4. Push → git push origin main
5. Verificar → Ver GitHub Actions y sitio publicado
```

---

**¡Listo para empezar! 🚀**
