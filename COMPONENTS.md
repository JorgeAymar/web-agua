# Componentes UI — AguaVida

Guía de referencia de cada componente visual del proyecto. Para tokens de color, tipografía y espaciado, ver [`DESIGN.md`](DESIGN.md).

---

## Navbar

Barra de navegación fija en la parte superior. Transparent por defecto; cambia a glass al hacer scroll.

```html
<nav id="navbar">
  <div class="nav-inner">
    <span class="nav-logo">
      <span class="material-symbols-outlined nav-drop">water_drop</span>
      AguaVida
    </span>
    <ul class="nav-links">
      <li><a href="#seccion">Enlace</a></li>
    </ul>
    <a href="#consejos" class="btn-nav inner-glow">CTA</a>
  </div>
</nav>
```

**Comportamiento JS:** `#navbar.scrolled` se aplica cuando `window.scrollY > 60`, cambiando el fondo a `rgba(255,255,255,0.75)` con `backdrop-filter: blur(20px)`.

---

## Hero

Sección de pantalla completa con imagen de fondo y parallax.

```html
<section class="hero">
  <div class="hero-img-wrap">
    <img class="hero-bg" src="..." alt="..."/>  <!-- parallax target -->
  </div>
  <div class="hero-overlay"></div>              <!-- gradiente sobre imagen -->
  <div class="hero-content">
    <span class="badge">ETIQUETA</span>
    <h1 class="hero-title">Título</h1>
    <p class="hero-sub">Subtítulo</p>
    <div class="hero-btns">
      <a class="btn-primary inner-glow">CTA Principal</a>
      <a class="btn-glass">CTA Secundario</a>
    </div>
    <div class="hero-trust">...</div>
  </div>
  <div class="wave-bottom">...</div>            <!-- ola SVG de transición -->
</section>
```

**Parallax JS:**
```js
window.addEventListener('scroll', () => {
  heroBg.style.transform = `scale(1.1) translateY(${window.scrollY * 0.22}px)`;
});
```

---

## Badge

Etiqueta de categoría pequeña sobre el título del hero.

```html
<span class="badge">PREMIUM HYDRATION</span>
```

Usa `--tertiary-fixed` (#c0e8ff) como fondo y `--on-tertiary-fixed` (#001e2b) como texto.

---

## Botones

### Primario
```html
<a class="btn-primary inner-glow">
  Texto <span class="material-symbols-outlined">arrow_forward</span>
</a>
```

### Secundario (glass)
```html
<a class="btn-glass">Ver más</a>
```

### Nav
```html
<a class="btn-nav inner-glow">Acción</a>
```

---

## Stat Card

Card de estadística con ícono, número animado y descripción.

```html
<div class="glass-card stat-card liquid-hover fade-in">
  <span class="material-symbols-outlined stat-icon">public</span>
  <div>
    <span class="stat-number" data-target="71">0</span>
    <span class="stat-unit">%</span>
  </div>
  <p>Descripción de la estadística</p>
</div>
```

**Animación JS:** `data-target` define el valor final del contador. El número anima desde 0 con easing cúbico cuando entra en el viewport.

---

## Feature Item

Ítem de característica con ícono, título y descripción. Existe en variante clara (glass) y oscura.

```html
<!-- Variante clara -->
<div class="feature-item glass-card">
  <div class="feature-icon-wrap">
    <span class="material-symbols-outlined">eco</span>
  </div>
  <div>
    <h3>Título</h3>
    <p>Descripción.</p>
  </div>
</div>

<!-- Variante oscura -->
<div class="feature-item dark-card">
  <div class="feature-icon-wrap dark">
    <span class="material-symbols-outlined">grass</span>
  </div>
  <div>
    <h3>Título</h3>
    <p>Descripción.</p>
  </div>
</div>
```

---

## Tracker Card

Sección con barra de progreso animada e imagen.

```html
<div class="tracker-card glass-card fade-in">
  <div class="tracker-blob"></div>   <!-- decoración difuminada -->
  <div class="tracker-text">
    <span class="label-caps">ETIQUETA</span>
    <h2>Título</h2>
    <p>Descripción.</p>
    <div class="progress-bar-wrap">
      <div class="progress-bar">
        <div class="progress-fill"></div>  <!-- shimmer via ::after -->
      </div>
    </div>
    <div class="progress-labels">
      <span>Etiqueta izquierda</span>
      <span class="accent">Etiqueta derecha</span>
    </div>
  </div>
  <div class="tracker-img fade-in">
    <img src="..." alt="..."/>
  </div>
</div>
```

---

## Gallery Item

Tarjeta de imagen con caption que aparece al hacer hover.

```html
<div class="gallery-item liquid-hover fade-in">
  <img src="..." alt="Descripción"/>
  <div class="gallery-caption">Nombre</div>
</div>
```

El `.gallery-caption` usa `transform: translateY(100%)` por defecto y `translateY(0)` al hover. La imagen hace zoom con `scale(1.1)`.

---

## Testimonial Item

Cita con borde izquierdo en sección oscura.

```html
<div class="testimonial-item">
  <p>"Texto de la cita."</p>
  <div class="testimonial-author">
    <span class="author-name">Nombre</span>
    <span class="author-role">Cargo o institución</span>
  </div>
</div>
```

El borde izquierdo usa `--secondary-container` (`#316bf3`).

---

## Rating Card

Tarjeta compacta con estrellas y puntuación.

```html
<div class="rating-card glass-card">
  <div class="stars">
    <span class="material-symbols-outlined" style="font-variation-settings:'FILL' 1">star</span>
    <!-- repetir 5 veces -->
  </div>
  <p class="rating-label">Etiqueta</p>
  <p class="rating-score">Puntuación</p>
</div>
```

---

## Tip Card

Tarjeta de consejo con ícono, título y texto corto. Tiene efecto ripple al hacer click.

```html
<div class="tip-card glass-card liquid-hover">
  <span class="material-symbols-outlined tip-icon">shower</span>
  <h3>Título</h3>
  <p>Descripción breve.</p>
</div>
```

**Ripple JS:** Al hacer click se inserta un `<span>` con `animation: ripple 0.6s linear` que escala desde el punto de click.

---

## Fade In

Cualquier elemento puede tener animación de entrada al scrollear.

```html
<div class="fade-in">Contenido</div>
```

**Cómo funciona:**
1. El elemento empieza con `opacity: 0` y `translateY(40px)`
2. `IntersectionObserver` detecta cuando el elemento entra al viewport (threshold 12%)
3. Se agrega la clase `.visible` con un delay escalonado de `90ms × índice`

---

## Label Caps

Etiqueta en mayúsculas para encabezar secciones.

```html
<span class="label-caps">TEXTO EN MAYÚSCULAS</span>
```

Color `--secondary`, `font-size: 0.75rem`, `letter-spacing: 0.1em`.

---

## Footer

```html
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-logo">Marca</div>
      <p class="footer-copy">© Año. Descripción.</p>
    </div>
    <div class="footer-links">
      <a href="#">Enlace</a>
    </div>
    <div class="footer-icons">
      <div class="footer-icon">
        <span class="material-symbols-outlined">share</span>
      </div>
    </div>
  </div>
</footer>
```
