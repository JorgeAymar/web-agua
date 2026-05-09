# AguaVida — El Agua, Fuente de Vida

Sitio web educativo de una sola página sobre la importancia del agua en el planeta. Construido con **HTML, CSS y JavaScript puros** — sin frameworks, sin bundlers, sin dependencias `npm`. El sistema visual está basado en el diseño **AquaPure Landing Page** generado con [Google Stitch](https://stitch.withgoogle.com/).

![Vanilla JS](https://img.shields.io/badge/JS-Vanilla-f7df1e?logo=javascript&logoColor=000)
![CSS3](https://img.shields.io/badge/CSS3-modern-1572b6?logo=css3&logoColor=fff)
![No build](https://img.shields.io/badge/build-none-brightgreen)
![Responsive](https://img.shields.io/badge/responsive-mobile%20%E2%86%92%20desktop-0051d5)

![Hero](https://images.unsplash.com/photo-1505118380757-91f5f5632de0?w=1200)

---

## Tabla de contenidos

- [Demo](#demo)
- [Por qué este proyecto](#por-qué-este-proyecto)
- [Características](#características)
- [Tecnologías](#tecnologías)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Instalación y uso](#instalación-y-uso)
- [Sistema de diseño](#sistema-de-diseño)
- [Secciones](#secciones)
- [Personalización](#personalización)
- [Accesibilidad y rendimiento](#accesibilidad-y-rendimiento)
- [Navegadores soportados](#navegadores-soportados)
- [Documentación](#documentación)
- [Licencia](#licencia)

---

## Demo

Abre [`index.html`](index.html) en tu navegador. No requiere build, servidor ni `node_modules`.

> **Tip:** para evitar problemas de caché de fuentes y de scroll, sirve la carpeta con un servidor estático (ver [Instalación y uso](#instalación-y-uso)).

---

## Por qué este proyecto

- Demostrar que **HTML/CSS/JS modernos** alcanzan para una landing page atractiva sin Tailwind, React ni un paso de build.
- Servir como **plantilla de referencia** del sistema de diseño AquaPure (glassmorphism, dark cards, fuentes variables, parallax sutil).
- Documentar tokens y componentes reutilizables en archivos `.md` separados para que el sistema sea **trasplantable** a otros proyectos.

---

## Características

- Navbar fijo con efecto **glass** al hacer scroll
- **Hero** a pantalla completa con parallax suave
- **Contadores animados** con `requestAnimationFrame` y easing cúbico
- Aparición progresiva con `IntersectionObserver` (`fade-in` escalonado)
- **Galería** interactiva con caption deslizante al hover
- Barra de **progreso** con animación shimmer
- Efecto **ripple** en tarjetas al hacer click
- **Smooth scroll** entre secciones
- Diseño **responsive** (móvil, tablet, escritorio)
- Iconografía vía **Material Symbols** (sin librerías JS)

---

## Tecnologías

| Capa | Herramienta |
|---|---|
| Marcado | HTML5 semántico |
| Estilos | CSS3 (custom properties, grid, flexbox, `backdrop-filter`) |
| Interactividad | JavaScript ES2020 (sin dependencias) |
| Tipografía | Google Fonts — Plus Jakarta Sans + Manrope |
| Iconos | Google Material Symbols Outlined |
| Imágenes | Unsplash (hotlink) |

---

## Estructura del proyecto

```
web-agua/
├── index.html          # Estructura HTML y contenido
├── styles.css          # Sistema de diseño y estilos
├── script.js           # Interactividad y animaciones
├── README.md           # Este archivo
├── DESIGN.md           # Tokens del sistema de diseño
├── COMPONENTS.md       # Documentación de componentes UI
└── CHANGELOG.md        # Historial de cambios
```

---

## Instalación y uso

Clona el repositorio:

```bash
git clone https://github.com/JorgeAymar/web-agua.git
cd web-agua
```

### Opción A — Abrir directamente
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

### Opción B — Servidor estático local (recomendado)
```bash
# con Python 3
python3 -m http.server 8000

# o con Node
npx serve .

# o con PHP
php -S localhost:8000
```
Luego abre [http://localhost:8000](http://localhost:8000).

---

## Sistema de diseño

Basado en los tokens del diseño **AquaPure** de Google Stitch:

| Token | Valor |
|---|---|
| Color primario | `#001736` |
| Color secundario | `#0051d5` |
| Fondo claro | `#f7f9fb` |
| Fuente titular | Plus Jakarta Sans (400–800) |
| Fuente cuerpo | Manrope (400–700) |
| Border radius (cards) | `32px` |
| Border radius (botones) | `9999px` |
| Efecto base | `backdrop-filter: blur()` + bordes translúcidos |

Ver [`DESIGN.md`](DESIGN.md) para la paleta completa, escala tipográfica, sombras y espaciados.

---

## Secciones

| # | Sección | Descripción |
|---|---|---|
| 1 | Hero | Imagen full-bleed con parallax, badge, doble CTA y trust avatars |
| 2 | Datos | 4 estadísticas clave con contadores animados e iconos Material |
| 3 | Importancia | Grid con texto, dark card y imagen lateral |
| 4 | Tracker | Barra de progreso animada + imagen rotada |
| 5 | Galería | 6 fotografías con efecto hover y caption |
| 6 | Testimoniales | Sección oscura con citas + grid de consejos |
| 7 | Footer | Links de navegación, íconos sociales y copyright |

---

## Personalización

**Cambiar colores y tipografía:** edita las custom properties al inicio de [`styles.css`](styles.css).

**Cambiar contenido:** todo el texto vive en [`index.html`](index.html); no hay datos en JSON ni en JS.

**Reemplazar imágenes:** sustituye las URLs de Unsplash por rutas locales (ej. `assets/hero.jpg`) y crea la carpeta `assets/`.

**Añadir secciones:** sigue la convención `<section class="section">` o `section-light` / `section-dark` y aplica `.fade-in` a los hijos para que el `IntersectionObserver` los anime.

---

## Accesibilidad y rendimiento

- Estructura semántica con `<nav>`, `<section>`, `<footer>` y headings jerárquicos.
- Idioma declarado en `<html lang="es">`.
- Imágenes con `alt` descriptivo (vacío en decorativas).
- Animaciones disparadas solo cuando el elemento entra en viewport — sin trabajo en background.
- Cero dependencias = **0 KB** de JS de terceros.

> **Mejoras pendientes:** respetar `prefers-reduced-motion`, lazy loading explícito en imágenes, `aria-label` en botones icon-only del footer.

---

## Navegadores soportados

Probado en versiones recientes de Chrome, Firefox, Safari y Edge. Requiere soporte de:

- CSS Custom Properties
- `backdrop-filter` (con `-webkit-` prefix donde aplique)
- `IntersectionObserver`
- ES2020 (`?.`, `??`)

---

## Documentación

| Archivo | Contenido |
|---|---|
| [`DESIGN.md`](DESIGN.md) | Tokens de color, tipografía, espaciado y componentes CSS |
| [`COMPONENTS.md`](COMPONENTS.md) | Guía de uso de cada componente UI |
| [`CHANGELOG.md`](CHANGELOG.md) | Historial de versiones y cambios |

---

## Licencia

Proyecto educativo de uso libre. Las imágenes provienen de [Unsplash](https://unsplash.com/license) bajo su licencia gratuita.
