# Stoa.Hoy — Sistema de Diseño

Sistema de diseño del canal de estoicismo **@Stoa.Hoy** (Instagram) y **@Stoa-Hoy** (YouTube). Cubre el contenido visual: carruseles, reels y plantillas de publicaciones.

---

## Contexto del canal

Stoa.Hoy es un canal en español dedicado a la filosofía estoica: Epicteto, Marco Aurelio, Séneca y los principios de la Stoa aplicados a la vida contemporánea.

**Plataformas:** Instagram (carrusel 4:5 · 1080×1350) · YouTube Shorts (9:16 · 1080×1920)
**Idioma:** Español
**Fuentes de inspiración:** Enquiridión (Epicteto) · Meditaciones (Marco Aurelio) · Cartas a Lucilio (Séneca)

---

## Fundamentos visuales

### Filosofía estética
Mármol, antigüedad clásica, editorial de lujo. La estética evoca los escritos originales, los bustos de piedra, el peso del pensamiento. Cada elemento justifica su presencia. Sin adornos superfluos.

### Marca y handles
La **marca** y las **direcciones** son cosas distintas:
- **`STOA · HOY`** es el wordmark. Es el sello neutro que se estampa en láminas y frames (portada, hook, citas, "solo imagen"). Sin `@`, sin punto ni guion — válido en cualquier plataforma.
- **`@Stoa.Hoy`** (Instagram) y **`@Stoa-Hoy`** (YouTube) son las direcciones. Solo aparecen juntas en la lámina/pantalla de **cierre o CTA**, nunca como sello en mitad del contenido.

Así un mismo vídeo o carrusel sirve para ambas plataformas: el sello es neutro y solo el cierre dirige a cada cuenta.

### Tipografía
| Rol | Familia | Uso |
|---|---|---|
| Display / Cuerpo | Cormorant Garamond | Títulos, citas, listas, body copy |
| Kickers / Labels | Hanken Grotesk | Etiquetas, números de lámina, handles |

- **Cormorant Garamond** semibold para headings grandes, medium para citas, regular para body.
- **Hanken Grotesk** siempre uppercase con `letter-spacing: 0.34em` para kickers; sin uppercase para handles y atribuciones.

### Paleta cromática
| Token | Valor | Uso |
|---|---|---|
| `--cream-100` | `#F6F2EA` | Fondo claro principal |
| `--ink-800` | `#1A1714` | Fondo oscuro principal |
| `--accent` | `#A98B63` | Divisores, kickers, comillas, números |
| `--text-primary-light` | `#26221C` | Texto sobre fondo claro |
| `--text-primary-dark` | `#EDE6D8` | Texto sobre fondo oscuro |
| `--text-muted-light` | `#8A8170` | Pie de slide / notas |
| `--text-muted-dark` | `#9A917E` | Pie de slide oscuro |

### Superficies
Siempre **gradientes radiales**, nunca planos. Luz desde arriba-izquierda en claros, desde centro-superior en oscuros. Evocan la luz de estudio sobre piedra.

- `--surface-light`: base para láminas interiores (conceptos, listas, práctica)
- `--surface-dark`: portada, lámina de contraste, cierre

### Ritmo de fondos en carrusel
Portada **oscura** → 2-3 láminas **claras** → 1 lámina **oscura** (contraste) → 2 láminas **claras** → Cierre **oscuro**. Máximo 2 alternaciones de paleta por carrusel.

### Divisor de acento
`56px × 2px` en color `--accent`. Separa siempre el heading del cuerpo/lista.

### Espaciado en slides
- Padding: `100px vertical × 96px horizontal`
- Kicker → contenido: `~48px`
- Heading → divisor: `36px`
- Divisor → body: `44px`

### Imágenes
Bustos de mármol, esculturas clásicas, paisajes serenos. Paleta neutra o fría. Sin colores saturados. Los placeholders usan franjas diagonales sutiles con etiqueta monospaced.

### Sin emoji, sin gradientes de color, sin esquinas muy redondeadas.

---

## Contenido y voz

### Tono
Reflexivo, filosófico. Sin urgencia comercial. Sin hipérbole. Segunda persona singular (tú, te, tu). Oraciones completas con precisión léxica.

### Patrones de copy
| Elemento | Ejemplo |
|---|---|
| Kicker | `ESTOICISMO · EPICTETO` / `DEPENDE DE TI` / `EL ERROR` |
| Título | "La dicotomía del control" · "Todo sufrimiento nace de confundirlos" |
| Cita | «Hay cosas que dependen de nosotros y cosas que no.» — Epicteto |
| Body | Oraciones completas, un sola idea por slide, vocabulario preciso |
| Prompt | "Pregúntate hoy: «¿Esto depende de mí?»" |
| CTA | "Sígueme para estoicismo cada día" |

### Estructura del carrusel (8 láminas)
1. **Portada** (oscura): tema + imagen opcional de mármol
2. **Principio** (clara): cita fundacional del filósofo
3. **Lámina A** (clara): lista o concepto positivo / "lo que SÍ"
4. **Lámina B** (oscura): contraste / "lo que NO"
5. **Lámina C** (clara): el error / consecuencia / desarrollo
6. **Lámina D** (clara): la solución / libertad / reencuadre
7. **Práctica** (clara): ejercicio reflexivo, prompt de journaling
8. **Cierre** (oscuro): cita de cierre + CTA + handle

---

## Fuentes de imágenes

### Dónde encontrar bustos y esculturas de mármol (gratis)
| Fuente | URL | Notas |
|---|---|---|
| **Unsplash** | unsplash.com | Busca: `marble bust`, `roman sculpture`, `ancient bust` |
| **Pexels** | pexels.com | Busca: `classical statue`, `marble sculpture`, `greek bust` |
| **Wikimedia Commons** | commons.wikimedia.org | Fuente de museos (Louvre, Capitolinos). Sin restricciones. |
| **The Met** | metmuseum.org/art/collection | Obras en dominio público, descarga directa |

### Términos de búsqueda recomendados (en inglés, más resultados)
`marble bust` · `roman bust` · `hellenistic sculpture` · `stoic philosopher` · `ancient marble portrait` · `museum bust` · `white marble sculpture` · `classical portrait`

### Qué buscar en una buena foto
- **Fondo oscuro o negro** → integra con láminas oscuras sin esfuerzo
- **Fondo claro neutro o gris** → integra con láminas claras
- **Ángulo lateral o en 3/4** → más dramático que el frontal plano
- **Iluminación lateral** → resalta el volumen del mármol
- **Resolución mínima:** 1500 × 1500 px para exportar a 1080 × 1350 con calidad

### Para los "Solo imagen" con texto encima
Cualquier foto funciona porque el scrim oscuro del diseño protege la legibilidad del texto. Puedes usar paisajes serenos, cielos despejados o texturas de piedra si no tienes bustos.

---

## Archivos

| Archivo | Descripción |
|---|---|
| `styles.css` | Entrada de tokens CSS |
| `tokens/colors.css` | Paleta completa de color |
| `tokens/typography.css` | Tipografía, escala y familias |
| `tokens/spacing.css` | Espaciado y dimensiones de slide |
| `guidelines/` | Tarjetas de sistema de diseño |
| `Carrusel - Dicotomia del control.dc.html` | Carrusel de ejemplo completo |
| `Plantilla Carrusel.dc.html` | Plantilla para nuevos carruseles |
