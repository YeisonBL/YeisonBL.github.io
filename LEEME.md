# Portafolio – Yeison Buitrago

## Estructura del proyecto

```
mi-portafolio/
├── _quarto.yml                        # Configuración del sitio (tema, navbar, etc.)
├── index.qmd                          # Landing page (página de inicio)
├── about.qmd                          # Página "Sobre mí"
├── styles.css                         # Estilos personalizados
├── .nojekyll                          # Necesario para GitHub Pages
├── assets/                            # ← CREA esta carpeta y pon imágenes aquí
│   ├── vis-bogota-preview.png
│   └── cv-updater-preview.png
└── projects/
    ├── index.qmd                      # Lista de proyectos (se genera automáticamente)
    ├── vis-segregacion-bogota.qmd     # Proyecto 1
    └── cv-actualizador-ia.qmd        # Proyecto 2
```

---

## Cómo publicar en GitHub Pages

### 1. Instalar Quarto
→ https://quarto.org/docs/get-started/

### 2. Renderizar el sitio
```bash
cd mi-portafolio
quarto render
```
Esto genera la carpeta `docs/` con el HTML del sitio.

### 3. Subir a GitHub
```bash
git init
git add .
git commit -m "Primer commit: portafolio inicial"
git remote add origin https://github.com/YeisonBL/YeisonBL.github.io
git push -u origin main
```

### 4. Activar GitHub Pages
- Ve a tu repo en GitHub
- Settings → Pages
- Source: **Deploy from a branch**
- Branch: `main` / carpeta: `/docs`
- Guarda y espera 1-2 minutos
- Tu sitio estará en: `https://YeisonBL.github.io`

---

## Cómo agregar contenido a los proyectos

Busca las secciones marcadas con `⚠️ PENDIENTE` en los archivos `.qmd` y reemplázalas con tu contenido real.

Los archivos `.qmd` son como Markdown normal — puedes escribir texto, pegar código Python con bloques de código, e insertar imágenes.
