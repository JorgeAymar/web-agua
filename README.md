# 💧 El Agua - Fuente de Vida

Página web educativa sobre la importancia del agua en el planeta, construida con HTML, CSS y JavaScript puros, sin frameworks ni dependencias externas.

## Vista previa

![Hero](https://images.unsplash.com/photo-1505118380757-91f5f5632de0?w=800)

## Características

- **Navbar fijo** que cambia de fondo al hacer scroll
- **Hero con parallax** y imagen de fondo a pantalla completa
- **Contadores animados** en la sección de estadísticas
- **Fade-in al scrollear** en todas las secciones usando `IntersectionObserver`
- **Galería de imágenes** con efecto hover y caption deslizante
- **Efecto ripple** al hacer click en las tarjetas de consejos
- **Smooth scroll** en los links de navegación
- Diseño **responsive** adaptado a móvil, tablet y escritorio

## Estructura del proyecto

```
web-agua/
├── index.html   # Estructura y contenido de la página
├── styles.css   # Estilos visuales y animaciones CSS
├── script.js    # Interactividad: parallax, contadores, fade-in, ripple
└── README.md
```

## Secciones

| Sección | Descripción |
|---|---|
| Hero | Imagen de océano con parallax y texto animado |
| Datos | 4 estadísticas clave con contadores animados |
| Importancia | Texto + imagen con categorías (ecosistemas, agricultura, salud) |
| Galería | 6 fotografías de entornos acuáticos con hover interactivo |
| Consejos | 6 tips para ahorrar agua con efecto ripple |

## Tecnologías

- HTML5 semántico
- CSS3 (Grid, Flexbox, animaciones, backdrop-filter)
- JavaScript vanilla (IntersectionObserver, requestAnimationFrame)
- Imágenes de [Unsplash](https://unsplash.com)

## Uso

Clona el repositorio y abre `index.html` en tu navegador:

```bash
git clone https://github.com/JorgeAymar/web-agua.git
cd web-agua
open index.html
```

No requiere instalación ni servidor.
