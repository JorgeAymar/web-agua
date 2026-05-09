# Sistema de Diseño — AguaVida

Este documento describe los tokens visuales y componentes CSS del proyecto, extraídos del diseño **AquaPure Landing Page** generado con [Google Stitch](https://stitch.withgoogle.com/).

---

## Paleta de colores

Todos los colores están definidos como variables CSS en `:root` en `styles.css`.

### Colores principales

| Variable | Hex | Uso |
|---|---|---|
| `--primary` | `#001736` | Títulos, textos oscuros, navbar logo |
| `--secondary` | `#0051d5` | Botones CTA, iconos, acentos |
| `--tertiary` | `#001a25` | Fondos oscuros alternativos |
| `--primary-container` | `#002b5b` | Dark cards, feature item oscuro |
| `--tertiary-container` | `#003041` | Sección oscura alternativa |
| `--tertiary-fixed` | `#c0e8ff` | Badge del hero |
| `--on-tertiary-fixed` | `#001e2b` | Texto sobre badge |

### Colores de superficie

| Variable | Hex | Uso |
|---|---|---|
| `--surface` | `#f7f9fb` | Fondo base del body |
| `--surface-low` | `#f2f4f6` | Secciones alternadas claras |
| `--surface-container` | `#eceef0` | Barra de progreso, fondos internos |
| `--on-surface` | `#191c1e` | Texto principal |
| `--on-surface-variant` | `#43474f` | Texto secundario, subtítulos |
| `--outline-variant` | `#c4c6d0` | Bordes sutiles, separadores |

### Colores on-brand

| Variable | Hex | Uso |
|---|---|---|
| `--on-primary` | `#ffffff` | Texto sobre fondo `--primary` |
| `--on-primary-container` | `#7594ca` | Texto sobre dark cards |
| `--secondary-container` | `#316bf3` | Borde izquierdo en testimoniales |

---

## Tipografía

### Familias

| Variable | Fuente | Uso |
|---|---|---|
| `--font-headline` | Plus Jakarta Sans | Títulos, navbar, botones |
| `--font-body` | Manrope | Cuerpo de texto, labels, subtítulos |

Las fuentes se cargan desde Google Fonts:

```html
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;700;800&family=Manrope:wght@400;500;700&display=swap" rel="stylesheet"/>
```

### Escala tipográfica

| Nombre | Tamaño | Peso | Letra-spacing | Uso |
|---|---|---|---|---|
| headline-xl | `clamp(3rem, 8vw, 5.5rem)` | 800 | `-0.03em` | Título hero |
| headline-lg | `clamp(2rem, 4vw, 3rem)` | 700 | `-0.02em` | Títulos de sección |
| headline-md | `1rem` | 700 | — | Títulos de card/feature |
| body-lg | `1.15rem` | 400 | — | Párrafos de importancia |
| body-md | `1.05rem` | 400 | — | Párrafos generales |
| label-caps | `0.75rem` | 700 | `0.1em` | Etiquetas en mayúsculas |

---

## Espaciado

| Variable | Valor | Uso |
|---|---|---|
| `--section-gap` | `7rem` | Padding vertical entre secciones |
| `container max-width` | `1200px` | Ancho máximo del contenedor |
| `container padding` | `0 2rem` | Padding horizontal del contenedor |

---

## Border radius

| Variable | Valor | Uso |
|---|---|---|
| `--radius-card` | `32px` | Cards principales, galería |
| `--radius-btn` | `9999px` | Botones (pill shape) |
| `--radius-xl` | `24px` | Feature items, tracker, tips |

---

## Componentes CSS

### `.glass-card`

Card con efecto vidrio esmerilado.

```css
.glass-card {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(24px);
  border: 1px solid rgba(255, 255, 255, 0.4);
  box-shadow: 0 8px 32px rgba(0, 23, 54, 0.06);
}
```

**Uso:** stat cards, feature items, tracker, tip cards, rating card.

---

### `.liquid-hover`

Animación de elevación al hover, evoca el movimiento del agua.

```css
.liquid-hover {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.liquid-hover:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 81, 213, 0.12);
}
```

**Uso:** stat cards, gallery items, tip cards.

---

### `.inner-glow`

Reflejo interno sutil en botones CTA.

```css
.inner-glow {
  box-shadow: inset 0 1px 1px rgba(255, 255, 255, 0.3);
}
```

**Uso:** `.btn-primary`, `.btn-nav`.

---

### `.btn-primary`

Botón principal de acción.

```css
.btn-primary {
  background: var(--secondary);
  color: #fff;
  padding: 1rem 2.2rem;
  border-radius: var(--radius-btn);
  font-family: var(--font-headline);
  font-weight: 700;
  box-shadow: 0 8px 24px rgba(0, 81, 213, 0.25);
}
```

---

### `.btn-glass`

Botón secundario con efecto cristal.

```css
.btn-glass {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(24px);
  border: 1px solid rgba(255, 255, 255, 0.4);
  color: var(--secondary);
  padding: 1rem 2.2rem;
  border-radius: var(--radius-btn);
}
```

---

### `.fade-in` / `.fade-in.visible`

Animación de entrada al hacer scroll.

```css
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```

La clase `.visible` se agrega vía JavaScript con `IntersectionObserver`.

---

### `.progress-fill::after` — Shimmer

Animación de brillo deslizante en la barra de progreso.

```css
.progress-fill::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0%   { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}
```

---

## Iconos

Se usan **Material Symbols Outlined** de Google.

```html
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap" rel="stylesheet"/>
```

Para ícono relleno (filled):

```html
<span class="material-symbols-outlined" style="font-variation-settings:'FILL' 1">water_drop</span>
```

### Íconos utilizados en el proyecto

| Ícono | Sección |
|---|---|
| `water_drop` | Navbar logo |
| `public` | Stat: cobertura terrestre |
| `water_drop` | Stat: agua dulce |
| `groups` | Stat: personas sin acceso |
| `favorite` | Stat: cuerpo humano |
| `eco` | Feature: ecosistemas |
| `grass` | Feature: agricultura |
| `health_and_safety` | Feature: salud |
| `shower` | Tip: duchas |
| `build` | Tip: fugas |
| `thunderstorm` | Tip: agua de lluvia |
| `recycling` | Tip: contaminación |
| `arrow_forward` | Botón hero |
| `star` | Rating |
| `share` / `mail` | Footer |
