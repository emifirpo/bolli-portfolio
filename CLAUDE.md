# Florencia Bollini — Portfolio Site

Sitio web personal y portfolio profesional de **Florencia Bollini**, diseñadora UX/UI argentina.

---

## Archivo principal

`FlorenciaBollini_Portfolio.jsx` — Componente React (JSX) único, autocontenido. Todo el CSS vive dentro del componente via `<style>` tags inline. No hay archivos externos de estilos, dependencias externas, ni router. Se renderiza directamente en el previewer de Cowork.

---

## Stack

- **React** (hooks: useState, useEffect, useRef)
- **Google Fonts** via `@import` en el style tag: `Playfair Display` + `Inter`
- **CSS inline** + `<style>` global con keyframes y clases utilitarias
- **Sin librerías de animación externas** — todo motion es CSS + JS nativo

---

## Sobre Florencia

| Campo | Dato |
|---|---|
| Email | florencia.bollini@gmail.com |
| Teléfono | +54 9 223 632 3721 |
| LinkedIn | linkedin.com/in/florencia-bollini |
| Ubicación | Mar del Plata, Argentina |

**Educación:**
- Tecnicatura en Programación — UTN Mar del Plata (2021–2027)
- Diplomatura en Diseño UX/UI — UTN Buenos Aires (2025)

**Herramientas:** Figma, Adobe Illustrator, InDesign

**Proyectos documentados:**
1. **PetControl** — App Android para gestión de mascotas (Diplomatura UTN)
2. **SHEIN Redesign** — Rediseño web de experiencia de compra (Diplomatura UTN)

---

## Sistema de diseño

### Colores
| Token | Valor | Uso |
|---|---|---|
| `bg` | `#F6F5F2` | Fondo principal (crema cálido) |
| `bgAlt` | `#EFECE7` | Fondo alternativo |
| `text` | `#0D0D0D` | Texto primario |
| `muted` | `#7A7873` | Texto secundario |
| `accent` | `#8B1A1A` | Vino tinto (marca) |
| `dark` | `#111110` | Secciones oscuras |

### Tipografía
- **Playfair Display** — Titulares editoriales, nombre hero, nombre de sección (italic)
- **Inter** — Todo lo demás: cuerpo, UI, labels, nav

### Motion
- Easing principal: `cubic-bezier(0.16, 1, 0.3, 1)` — suave, orgánico
- Scroll reveals via `IntersectionObserver` + stagger por delay
- Custom cursor: dot 8px + ring 32px con lag
- Marquee CSS: `@keyframes marquee` en tira oscura entre hero y about

---

## Estructura de secciones

1. **NAV** — Fixed, transparente → blur al hacer scroll. Logo "FB". Links + lang toggle ES/EN.
2. **HERO** — Viewport completo. "B" monogram de fondo. Nombre tipográfico grande (Playfair). Statement editorial en italic.
3. **MARQUEE** — Tira oscura con disciplinas en loop continuo.
4. **ABOUT (01)** — Grid 1.4/0.6. Bio en 3 párrafos + sidebar con educación y herramientas.
5. **WORK (02)** — Lista indexada con rows expandibles. Click toggle muestra problema/objetivo/proceso.
6. **CONTACT (03)** — Sección oscura. CTA email + lista de contactos con hover animado.
7. **FOOTER** — Minimal. Copyright + tagline.

---

## Bilingüe

El objeto `T` tiene claves `es` y `en`. El estado `lang` controla qué versión se muestra. El toggle ES/EN está en la navbar.

---

## Principios del sitio (instrucciones del proyecto)

Este sitio se construye bajo un estándar top 1% de portfolios de diseño UX/UI. Ver las instrucciones completas del proyecto en la configuración de Cowork.

**No hacer nunca:**
- Gradientes genéricos, glassmorphism decorativo, blobs
- Grillas de cards iguales sin jerarquía
- "Hola soy X y me apasiona el diseño"
- Animaciones de juguete o excesivas
- Mockups flotantes sin propósito
- Layouts copiados de templates Framer/Webflow

**Siempre buscar:**
- Composición editorial con intención
- Motion que construye jerarquía, no que decora
- Tipografía con carácter y tensión visual
- Espacio en blanco inteligente
- Identidad visual propia y distinguible

---

## Para extender el sitio

- **Agregar proyecto:** Añadir objeto al array `cases` dentro de `T.es.work.cases` y `T.en.work.cases`
- **Cambiar acento:** Modificar `C.accent` en los tokens
- **Agregar sección:** Crear `<section id="nueva">`, agregar a la lista de IDs del IntersectionObserver del nav, y agregar link en `t.nav`
- **Foto real:** Reemplazar el bloque del monogram "B" en el hero con una imagen real usando `<img>` con `position: absolute` y `object-fit: cover`
