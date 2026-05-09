# Changelog — AguaVida

Historial de versiones del proyecto. Formato basado en [Keep a Changelog](https://keepachangelog.com/es/).

---

## [1.2.0] — 2026-05-09

### Añadido
- Sistema de diseño completo de **Google Stitch** (AquaPure Landing Page)
- Componente `.glass-card` con `backdrop-filter: blur(24px)`
- Componente `.liquid-hover` con animación de elevación al hover
- Componente `.inner-glow` para botones CTA
- Fuentes de Google: **Plus Jakarta Sans** (títulos) y **Manrope** (cuerpo)
- Iconografía con **Material Symbols Outlined**
- Badge de categoría en el hero
- Trust avatars con imágenes de usuarios
- Sección Tracker con barra de progreso animada (shimmer)
- Sección Testimoniales sobre fondo navy (`--primary`)
- Rating card con estrellas
- Footer con links y íconos sociales
- Variables CSS (design tokens) en `:root`
- Documentación: `DESIGN.md`, `COMPONENTS.md`, `CHANGELOG.md`

### Modificado
- Paleta de colores: de `#0077b6` a `#001736` / `#0051d5` (sistema AquaPure)
- Tipografía: de Segoe UI a Plus Jakarta Sans + Manrope
- Border radius de cards: de `1.2rem` a `32px`
- Botones con forma pill (`border-radius: 9999px`)
- Sección de consejos rediseñada como grid 2×2 dentro de sección dark
- README actualizado con tabla de documentación

---

## [1.1.0] — 2026-05-09

### Añadido
- Imágenes reales desde Unsplash en todas las secciones
- Archivo `script.js` con interactividad completa
- Parallax en la imagen del hero
- Fade-in con `IntersectionObserver`
- Contadores animados con `requestAnimationFrame` y easing cúbico
- Smooth scroll en todos los links de navegación
- Efecto ripple al hacer click en las tarjetas de consejos
- Navbar que cambia de fondo al hacer scroll
- Sección de galería con 6 fotografías y caption hover
- Sección de importancia con imagen lateral

### Modificado
- `styles.css` expandido con diseño visual completo
- Estructura HTML reorganizada en secciones semánticas

---

## [1.0.0] — 2026-05-09

### Añadido
- Archivo `index.html` con estructura HTML semántica básica
- Archivo `styles.css` con estilos básicos (sin framework)
- Archivo `script.js` vacío
- Repositorio inicializado en GitHub: `JorgeAymar/web-agua`
- `README.md` inicial

### Secciones iniciales
- Hero
- Estadísticas (lista)
- Importancia
- Consejos
- Footer
