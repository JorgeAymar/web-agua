# AguaVida — El Agua, Fuente de Vida

Sitio web educativo sobre la importancia del agua en el planeta. Construido con **HTML, CSS y JavaScript puros**, sin frameworks ni dependencias externas. El sistema visual está basado en el diseño **AquaPure Landing Page** generado con [Google Stitch](https://stitch.withgoogle.com/).

![Hero](https://images.unsplash.com/photo-1505118380757-91f5f5632de0?w=1200)

---

## Tabla de contenidos

- [Demo](#demo)
- [Características](#características)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Sistema de diseño](#sistema-de-diseño)
- [Secciones](#secciones)
- [Instalación](#instalación)
- [Documentación](#documentación)

---

## Demo

Abre `index.html` directamente en tu navegador. No requiere servidor ni instalación.

---

## Características

- Navbar fijo con efecto glass al hacer scroll
- Hero de pantalla completa con efecto parallax
- Contadores animados con `requestAnimationFrame`
- Fade-in al scrollear con `IntersectionObserver`
- Galería interactiva con caption deslizante al hover
- Barra de progreso con animación shimmer
- Efecto ripple en tarjetas al hacer click
- Smooth scroll entre secciones
- Diseño responsive (móvil, tablet, escritorio)

---

## Estructura del proyecto

```
web-agua/
├── index.html          # Estructura HTML y contenido
├── styles.css          # Sistema de diseño y estilos
├── script.js           # Interactividad y animaciones
├── README.md           # Este archivo
├── DESIGN.md           # Sistema de diseño (tokens, componentes)
├── COMPONENTS.md       # Documentación de componentes UI
└── CHANGELOG.md        # Historial de cambios
```

---

## Sistema de diseño

Basado en los tokens del diseño **AquaPure** de Google Stitch:

| Token | Valor |
|---|---|
| Color primario | `#001736` |
| Color secundario | `#0051d5` |
| Fuente titular | Plus Jakarta Sans |
| Fuente cuerpo | Manrope |
| Border radius (cards) | `32px` |
| Border radius (botones) | `9999px` |

Ver [`DESIGN.md`](DESIGN.md) para el sistema completo.

---

## Secciones

| Sección | Descripción |
|---|---|
| Hero | Parallax con imagen a pantalla completa, badge, CTA y trust avatars |
| Datos | 4 estadísticas clave con contadores animados e iconos Material |
| Importancia | Grid con texto, dark card y imagen lateral |
| Tracker | Barra de progreso animada + imagen con rotación |
| Galería | 6 fotografías con efecto hover y caption |
| Testimoniales | Sección oscura con citas y grid de consejos |
| Footer | Links de navegación, íconos sociales y copyright |

---

## Instalación

```bash
git clone https://github.com/JorgeAymar/web-agua.git
cd web-agua
open index.html   # macOS
# o simplemente arrastra index.html al navegador
```

---

## Documentación

| Archivo | Contenido |
|---|---|
| [`DESIGN.md`](DESIGN.md) | Tokens de color, tipografía, espaciado y componentes CSS |
| [`COMPONENTS.md`](COMPONENTS.md) | Guía de uso de cada componente UI |
| [`CHANGELOG.md`](CHANGELOG.md) | Historial de versiones y cambios |
