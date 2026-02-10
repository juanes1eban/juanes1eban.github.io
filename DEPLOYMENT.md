# Instrucciones de Deployment

## GitHub Pages está configurado automáticamente

Tu sitio se desplegará automáticamente cuando hagas push a la rama `main`.

## Pasos para publicar:

### 1. Asegurar que Git está configurado

```bash
git config --global user.name "Juan Valenzuela"
git config --global user.email "juan.esteban.valenzuela@gmail.com"
```

### 2. Agregar todos los archivos

```bash
git add .
```

### 3. Hacer commit de los cambios

```bash
git commit -m "feat: Sitio de CV completo con SEO optimizado"
```

### 4. Hacer push a GitHub

```bash
git push origin main
```

### 5. Verificar el deployment

- Ve a: https://github.com/juan-valenzuela-rodriguez/juan-valenzuela-rodriguez.github.io/actions
- Espera a que el workflow "Deploy Jekyll with GitHub Pages" termine (ícono verde ✅)
- Visita tu sitio en: https://juan-valenzuela-rodriguez.github.io/

## Configuración de GitHub Pages

Si es la primera vez:

1. Ve a tu repositorio en GitHub
2. Settings > Pages
3. Source: "GitHub Actions" (ya está configurado en el workflow)
4. El sitio se publicará automáticamente

## Troubleshooting

### Si el sitio no se despliega:

1. **Verifica que el repositorio sea público**
2. **Revisa el Actions log:**
   - https://github.com/juan-valenzuela-rodriguez/juan-valenzuela-rodriguez.github.io/actions
3. **Asegúrate de que el archivo workflow existe:**
   - `.github/workflows/jekyll-gh-pages.yml`

### Si ves un 404:

- Espera 2-3 minutos después del deployment
- Verifica que index.html existe en la raíz
- Limpia caché del navegador (Ctrl + Shift + R)

## Actualizaciones futuras

Para actualizar el contenido:

1. Edita `index.html`
2. Actualiza la fecha en `sitemap.xml`
3. Haz commit y push
4. El sitio se actualizará automáticamente

## Monitoreo

- **GitHub Actions:** https://github.com/juan-valenzuela-rodriguez/juan-valenzuela-rodriguez.github.io/actions
- **Sitio en vivo:** https://juan-valenzuela-rodriguez.github.io/
- **Verificación SEO:** https://search.google.com/search-console

## Mejoras futuras recomendadas

- [ ] Agregar Google Analytics
- [ ] Configurar dominio custom (ej: juanvalenzuela.dev)
- [ ] Agregar foto profesional
- [ ] Implementar modo oscuro
- [ ] Agregar sección de blog
- [ ] Crear página de portfolio con proyectos visuales
- [ ] Implementar versión en inglés
