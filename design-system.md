# Science with Design — Sistema de diseño

> Extraído directamente del archivo de Figma (`Science with design web`), página **"sistema de diseño"** (`node-id=1-2`) y contrastado con el frame **Home** del prototipo animado. Fuente de verdad para construir `style.css`.

## 1. Color

### Paleta base (con variaciones)

| Familia | Token Figma | Hex |
|---|---|---|
| **Terracota** | `terracota/900` | `#7E382B` |
| | `terracota/700` | `#B2513F` |
| | `terracota/500` (principal) | `#E66B54` |
| | `terracota/300` | `#EB734F` |
| | `terracota/orange` (acento extra) | `#F06329` |
| **Azul** | `azul/900` | `#233F58` |
| | `azul/700` | `#30597A` |
| | `azul/principal` | `#3D709C` |
| | `azul/300` | `#5491AD` |
| | `azul/100` | `#99D1DB` |
| **Ámbar** | `ambar/900` | `#F0914A` |
| | `ambar/700` | `#F7AB59` |
| | `ambar/principal` | `#FABA63` |
| | `ambar/300` | `#FCC96B` |
| | `ambar/100` | `#FFDEA1` |
| **Negro/gris** | `negro/principal` | `#0F0A0A` |
| | `negro/700` | `#494444` |
| | `negro/500` | `#837E7E` |
| | `negro/300` | `#BDB8B8` |
| | `negro/100` | `#F5F0F0` |

### Tokens semánticos (uso)

| Token | Hex | Uso previsto |
|---|---|---|
| `bg/primary` | `#F5F0F0` | Fondo principal (crudo/hueso) |
| `bg/secondary` | `#F5ECDE` | Fondo secundario (variante cálida) |
| `bg/inverse` | `#0F0A0A` | Fondo invertido (nav, secciones oscuras) |
| `text/primary` | `#0F0A0A` | Texto principal |
| `text/secondary` | `#494444` | Texto secundario |
| `text/muted` | `#837E7E` | Texto atenuado |
| `text/inverse` | `#F5F0F0` | Texto sobre fondo oscuro |
| `text/accent` | `#E66B54` | Texto/acento destacado — unificado con `terracota/500` (confirmado por Edudu: es el mismo color, no un duplicado) |

### Efectos

- **Noise**: textura de ruido, radio 4 — aplicada sobre ciertos fondos/imágenes (detectada en el frame Home; confirmar en qué secciones se usa según avancemos).

---

## 2. Tipografía

Tres familias: **Archivo** (sans, titulares y cuerpo), **Baskervville** (serif, CTAs/quotes — nota: es "Baskervville", no "Baskerville"), **Space Mono** (monoespaciada, detalles técnicos/caption).

| Estilo | Fuente | Tamaño | Peso | Line-height | Letter-spacing (em) | Letter-spacing (px, a ese tamaño) |
|---|---|---|---|---|---|---|
| `display_bigger` | Archivo Black | 148px | 900 | 0.75 | -0.08em | ≈ -11.8px |
| `display` | Archivo Black | 120px | 900 | 0.75 | -0.08em | ≈ -9.6px |
| `H1` | Archivo Black | 80px | 900 | 0.8 | -0.08em | -6.4px |
| `H2` | Archivo Black | 56px | 900 | 0.75 | -0.03em | ≈ -1.68px |
| `H3` | Archivo ExtraBold | 36px | 800 | 1.15 | -0.01em | ≈ -0.36px |
| `H4` | Archivo SemiBold | 24px | 600 | 1.3 | 0em | 0px |
| `body_big_display` | Archivo Medium | 36px | 500 | 1.3 | +0.07em | ≈ +2.52px |
| `body_big` | Archivo Regular | 24px | 400 | 1.3 | +0.07em | +1.68px |
| `body_big_highlight` | Space Mono Bold | 24px | 700 | 1.3 | +0.07em | +1.68px |
| `body_small` | Archivo Regular | 16px | 400 | 1.7 | +0.07em | +1.12px |
| `label` | Archivo Regular | 13px | 400 | 1.7 | +0.03em | +0.39px |
| `caption` | Space Mono Regular | 20px | 400 | 1.5 | +0.05em | +1px |
| `quote` | Baskervville Bold | 32px | 700 | 0.9 | 0em | 0px |
| `button` | Baskervville Bold | 20px | 700 | 0.9 | 0em | 0px |
| `CTA` | Baskervville Bold | 40px | 700 | 32px (fijo, no ratio) | 0em | 0px |
| `prefooter_cta` | Baskervville Bold | 96px | 700 | 0.9 | 0em | 0px |

Notas:
- **Corrección importante:** el letter-spacing que da Figma es un **porcentaje del tamaño de fuente**, no píxeles fijos (lo comprobé contrastando el valor de la variable con el tracking real renderizado en el hero: -8% de 80px = -6.4px, coincide exactamente). Por eso en CSS se implementa en `em` (ej. `-0.08em`), que escala igual que el porcentaje — usar px fijos daría un tracking distinto en cada breakpoint/tamaño responsive.
- Los estilos grandes (`display*`, `H1`, `H2`, `H3`) llevan tracking negativo cerrado — característica del look brutalista/suizo.
- Los estilos de cuerpo grande (`body_big*`) y `caption` llevan tracking positivo amplio (~+5/+7%) — intencionado, confirmado por Edudu.
- `line-height` está expresado como ratio (multiplicador del tamaño de fuente) salvo `CTA`, que usa un valor fijo en px (32px).
- **Corrección (sección "covers"):** `H2` lleva `line-height:0.75`, no `1.0` — confirmado por Edudu al construir el título "For starters, you can have a look at some covers".

---

## 3. Componentes detectados en la página "sistema de diseño" (para referencia futura)

Localizados en el frame `componentes` (`node-id 93:22`) — se documentarán en detalle cuando construyamos cada uno:

- `card` (con estado hover)
- `element:service card`
- `Nav block`
- `Button explore`
- `Button CTA`
- `Sec button` (botón secundario)
- `Input field`
- `PRE-FOOTER-CTA`
- `Work case` (2 variantes)
- `Footer`

---

*Generado automáticamente a partir de las variables de Figma del archivo. Si algún valor no coincide con lo que ves en el lienzo, avisa para revisarlo.*
