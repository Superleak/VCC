# Instrucciones persistentes — Canal de Estoicismo

## Estructura de todo video (Shorts/Reels)

Cada video que se cree debe seguir el patrón de **Video - La Reserva del Filósofo.dc.html** y **Video - El Resultado.dc.html**. Sin excepciones.

### Layout obligatorio

```
┌─────────────────────────┬──────────────────────────────────────────┐
│  Panel izquierdo FIJO   │  Panel derecho SCROLLABLE                │
│  position:fixed         │  margin-left:340px                       │
│  width:340px            │                                          │
│  Video animado          │  ▸ Bloque YouTube (título + desc + tags) │
│  (1080×1920 escalado)   │  ▸ Bloque Instagram (caption + 1r cmt)  │
│                         │                                          │
│  ──────────────────────  │  Cada bloque tiene botón "Copiar todo"  │
│  ⏺ Instagram  ⏺ YouTube │                                          │
│  (botones grabación)    │                                          │
└─────────────────────────┴──────────────────────────────────────────┘
```

- Panel izquierdo: `position:fixed; left:0; top:0; bottom:0; width:340px; background:#0E0D0B; overflow:hidden`
- Botones pegados al fondo del panel izquierdo: `position:fixed; left:0; bottom:0; width:340px; z-index:10` con gradiente `linear-gradient(to top, #0E0D0B 70%, transparent)`
- Panel derecho: `margin-left:340px; padding:32px 36px 32px 28px; display:flex; flex-direction:column; gap:28px; min-height:100vh`

### Botones de grabación MP4 (frame a frame)

Siempre dos botones: uno para **Instagram** (9:16 · 1080×1920) y otro para **YouTube Shorts** (9:16 · 1080×1920). El slide final (CTA) cambia según `window.__stoaPlatform`:
- `'ig'` → tarjetas "Guarda este video" + "Sígueme @Stoa.Hoy"
- `'yt'` → pantalla SUSCRÍBETE grande

La lógica de grabación es siempre la misma:
- Carga `html-to-image` + `mp4-muxer` locales
- Busca el Stage div (1080×1920) en el DOM
- Fija `window.__stoaPlatform` antes de grabar
- Captura frame a frame a 24fps con WebCodecs + H.264 (AVC)
- Descarga como `.mp4`

### Duración de videos

- **Reels/Shorts estándar**: 30 segundos máximo
- **Videos explicativos largos**: hasta 50 segundos si el tema lo requiere

### Estructura de slides (30s, 5 slides)

| Slide | Tiempo | Fondo | Contenido |
|-------|--------|-------|-----------|
| 01 | 0–6s | Oscuro | Portada: hook visual + título grande |
| 02 | 6–14s | Claro | El problema o el error |
| 03 | 14–22s | Oscuro | Cita del filósofo (Epicteto/Marco Aurelio/Séneca) |
| 04 | 22–28s | Claro | La solución / lo que sí controlas (lista 3 items) |
| 05 | 28–30s | Oscuro | CTA: IG tarjetas / YT SUSCRÍBETE |

Flash de corte en cada transición (`opacity: Math.max(0, 1 - Math.abs(t - at) / 0.1) * 0.14`).

### Imágenes finales (últimas pantallas del video)

Siempre hay **dos imágenes de cierre distintas** según plataforma:

**Instagram (4:5 · 1080×1350)**
- Fondo oscuro `--surface-dark`
- Kicker: "Para recordar"
- Cita de cierre en grande (itálica)
- Atribución al filósofo
- Dos tarjetas en la parte inferior: "Guarda este video" + "Sígueme en Instagram · @Stoa.Hoy"

**YouTube Shorts (9:16 · 1080×1920)**
- Fondo oscuro `--surface-dark`
- Wordmark STOA · HOY en acento
- Frase introductoria en itálica (ej. "Si esto te hizo pensar,")
- Titular gigante: **SUSCRÍBETE** (148px, semibold)
- Divisor de acento (56×3px)
- Línea de valor (ej. "Cada día, una idea que cambia cómo ves el mundo.")
- Handle @Stoa-Hoy + "YouTube · Estoicismo diario"

La plantilla reutilizable de estas imágenes está en **Plantilla CTA Final.dc.html**.

### Panel de textos SEO (panel derecho)

Siempre incluir dos bloques:

**YouTube** (con botón "Copiar todo"):
- Título (con hashtags al final)
- Descripción completa con bullets, separadores ━━━, y CTA → @Stoa-Hoy
- Tags (lista de palabras clave separadas por coma)

**Instagram** (con botón "Copiar todo"):
- Caption completo con hashtags
- Primer comentario (hashtags extra)

### Nombre del componente de animación

Cada video tiene su propio nombre de componente global (ej. `ReservaVideo`, `SoledadVideo`, `ResultadoVideo`). Nunca reutilizar el mismo nombre para evitar conflictos.

### Archivos de referencia

- `Video - La Reserva del Filósofo.dc.html` — plantilla canónica (50s, panel fijo)
- `Video - El Resultado.dc.html` — segunda implementación (30s, mismo patrón)
- `animations.jsx` — motor de animación (Stage, useTime, interpolate)

## Cómo arrancar los creadores (Servidor Local)

Para ejecutar `Creador_de_Carruseles.html` y `Creador_de_Videos.html` localmente sin problemas de CORS (requerido porque el creador de vídeos lee `./animations.jsx` mediante fetch):

1. **Levantar un servidor web local** en el directorio raíz del proyecto:
   `npx -y http-server -p 8080`
   *(Alternativa si no hay Node: `python -m http.server 8080`)*
2. **Acceder en el navegador Chrome** (necesario por soporte de `WebCodecs`/`VideoEncoder` al grabar vídeos):
   - Creador de Carruseles: [http://localhost:8080/Creador_de_Carruseles.html](http://localhost:8080/Creador_de_Carruseles.html)
   - Creador de Vídeos: [http://localhost:8080/Creador_de_Videos.html](http://localhost:8080/Creador_de_Videos.html)

