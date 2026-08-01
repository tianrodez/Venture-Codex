# Changelog

Todos los cambios notables de Venture Codex se documentaran en este archivo.

### [0.58.3] - 2026-07-24

Agregado campo de autor en package.json para la atribución adecuada. Agregado campo de icono en package.json para mostrar el icono de la extensión en VS Code Marketplace.

d70fba06582fdafcc6978f39defb93955
### [0.58.2] - 2026-07-24

Nombre del paquete cambiado a `venture-codex-theme` para evitar conflicto con un intento previo de publicación. Actualizado `package.json` con nuevo nombre, displayName, homepage y URL del repositorio.

## [0.58.1] - 2026-07-11

### Cambiado (HC Light - Colores de Sticky Scroll corregidos)

Se detecto que el sticky scroll (encabezado de funcion al hacer scroll) tenia fondo oscuro que no tenia sentido en HC Light.

Colores de sticky scroll alineados con Light theme:

| Clave | Antes (fuga de HC Dark) | Ahora (alineado con Light) |
|---|---|---|
| editorStickyScroll.background | #0F1818 (teal oscuro) | #D8CCC0 (warm taupe) |
| editorStickyScroll.headerBackground | #1B2025 (oscuro) | #D8CCC0 (warm taupe) |
| editorStickyScrollHover.background | #E0D8C8 | #D8CCC0 |
| sideBarStickyScroll.shadow | #00000080 | #00000050 |
| panelStickyScroll.shadow | #00000080 | #00000040 |
| terminalStickyScrollHover.background | #E0D8C8 | #D8CCC0 |

Causa: estos colores habian quedado con valores de HC Dark por el reemplazo masivo inicial del tema HC Light. Corregidos.

## [0.58.0] - 2026-07-11

### Cambiado (Renombrar High Contrast a High Contrast Dark)

Fix en el nombre del high contrast dark, agregarle el dark.

- Archivo: themes/venture-codex-high-contrast.json
  - name: Venture Codex High Contrast a Venture Codex High Contrast Dark
- Archivo: package.json
  - Theme label: Venture Codex High Contrast a Venture Codex High Contrast Dark

Ahora los 4 temas tienen nombres consistentes:

- Venture Codex Dark (vs-dark)
- Venture Codex Light (vs)
- Venture Codex High Contrast Dark (hc-black) - renombrado
- Venture Codex High Contrast Light (hc-light)

## [0.57.5] - 2026-07-11

### Cambiado (HC Light - Fondos de input menos claros, alineados con Light)

#FFFFFF para fondos de inputs/widgets era demasiado claro, causaba fatiga visual.

15 claves actualizadas de #FFFFFF (demasiado claro) a colores de Light theme:

| Elemento | Antes | Ahora | Light theme |
|---|---|---|---|
| input.background | #FFFFFF | #E0D5C8 | coincide |
| inputBox.background | #FFFFFF | #E0D5C8 | coincide |
| input.border | #3A3838 | #A8957A | coincide |
| input.foreground | #0F1818 | #1F3838 | coincide |
| input.placeholderForeground | #3A3838 | #8C7C70 | coincide |
| editorWidget.background | #FFFFFF | #E5DCD0 | coincide |
| editorSuggestWidget.background | #FFFFFF | #E5DCD0 | coincide |
| editorHoverWidget.background | #FFFFFF | #E5DCD0 | coincide |
| inlineChatInput.background | #FFFFFF | #E5DCD0 | coincide |
| settings.dropdownBackground | #FFFFFF | #E0D5C8 | coincide |
| settings.textInputBackground | #FFFFFF | #E0D5C8 | coincide |
| settings.numberInputBackground | #FFFFFF | #E0D5C8 | coincide |
| settings.checkboxBackground | #FFFFFF | #E0D5C8 | coincide |
| inputOption.activeBackground | #C8E0D0 | #B07818 | coincide |
| inputValidation.infoBackground | #E8DCC8 | #D8CCC0 | coincide |
| inputValidation.errorBackground | #F5D8D8 | #E8C8C0 | coincide |

#FFFFFF mantiene su uso correcto en foreground de badges/botones con fondos oscuros, igual que Light theme.

## [0.57.4] - 2026-07-11

### Cambiado (HC Light - Colores de seleccion alineados con Light)

#98A8B8 (azul-gris cool) usado para seleccion del selector de archivos. Light theme usa #C8A888 (bronce calido) para el mismo rol.

Colores de seleccion alineados con Light theme:

| Elemento | Antes | Ahora | Light theme |
|---|---|---|---|
| list.activeSelectionBackground | #98A8B8 | #C8A888 | coincide |
| list.focusBackground | #A8B8C8 | #D8CCC0 | coincide |
| selection.background | #98A8B8 | #C8A888 | coincide |
| list.activeSelectionForeground | #0F1818 | #1F3838 | coincide |
| editor.selectionBackground | #88B098 | #3A5A8C40 | coincide (lapis alfa) |
| terminal.selectionBackground | #88B098 | #C8A888 | coincide |
| editor.findMatchBackground | #FFE070 | #D4B580 | coincide |

## [0.57.3] - 2026-07-11

### Cambiado (HC Light - Remover #1F9058 de elementos chrome)

#1F9058 (verde bosque de sintaxis) tambien se usaba para elementos chrome como bordes, foregrounds de iconos, fondos hover. Light theme usa dorado #B07818 o naranja #C06820 para esos elementos.

164 claves actualizadas, cada una mapeada al color correspondiente de Light theme:

- Bordes (focusBorder, brackets) -> #D8CCC0 o #B07818
- Foregrounds de iconos (class, function, method) -> #C06820 o #8C7C70
- Fondos hover (button, extensionButton) -> #A07018 o #3A7A30
- Foregrounds de decoraciones (gitDecoration, etc.) -> #B07818
- Fondos de badges (badge, activityBarBadge) -> #B07818
- Iconos/info foregrounds -> #8C7C70

#1F9058 se mantiene solo para:
- 1 color: 	erminal.ansiGreen
- 18 tokenColors de sintaxis (Keyword, Storage Type, Function calls, etc.)
- 1 semanticTokenColor (*.defaultLibrary)

## [0.57.2] - 2026-07-11

### Cambiado (HC Light - Remover #1F7048 verde restante)

#1F7048 (verde medio) aun aparecia en 8 instancias de HC Light.

8 instancias reemplazadas con el verde bosque de Light theme #1F9058:

- 	extLink.activeForeground
- extensions.buttonHoverBackground
- extensionButton.prominentHoverBackground
- button.primaryHoverBackground
- editorLineNumber.activeForeground
- statusBarItem.prominentHoverBackground
- extensionButton.hoverBackground
- mergeEditor.conflict.handledFocused.border

## [0.57.1] - 2026-07-11

### Cambiado (HC Light - Remover #0F5838 verde restante)

#0F5838 (verde oscuro que NO existe en Light theme) aun aparecia en 155 instancias de HC Light.

155 instancias reemplazadas con el verde bosque de Light theme #1F9058:

- 137 colors section (symbolIcons, borders, activityBar, gitDecoration, notebook, testing, terminal symbols, extensions, chat, inlineEdit, markdownAlert, charts, scmGraph, comment views, panel titles, settings)
- 5 tokenColors (CSS Property Names, Markup - Bold-Italic, YAML Key, Markdown Checkbox Done)
- 1 semanticTokenColor (*.defaultLibrary)

## [0.57.0] - 2026-07-11

### Cambiado (HC Light - Alineado con colores de Light theme)

HC Light ahora usa exactamente los mismos colores que Light theme. Sin variantes oscuras, identidad visual coherente.

Colores de tokens alineados con Light (muestra):

| Token | Antes HC Light | Ahora HC Light | Light theme |
|---|---|---|---|
| Comments | #5A5040 | #8C7C70 | coincide |
| Variables | #0F1818 | #1F3838 | coincide |
| Keyword (Storage Type) | #0F5838 | #1F9058 | coincide |
| Function calls | #A04010 | #1F9058 | coincide |
| Operators | #5A5040 | #A07018 | coincide |
| Punctuation | #D8DCD0 | #5A4530 | coincide |
| Function decl | #0050A0 | #2C58A0 | coincide |
| Numbers | #A04010 | #C04020 | coincide |
| Strings | #705000 | #B07818 | coincide |
| Method decl | #0050A0 | #C06820 | coincide |
| Properties | #A04010 | #C06820 | coincide |
| Sub-methods | #0050A0 | #8C7C70 | coincide |
| Markdown - Heading | #006090 | #1F7888 | coincide |
| HTML Attributes | #006090 | #1F7888 | coincide |
| CSS Classes | #0050A0 | #2C58A0 | coincide |
| Python Type Hint | #0050A0 | #2C58A0 | coincide |
| JSX | #0050A0 | #C06820 | coincide |

UI Chrome alineado tambien (muestra):

| Elemento | Antes | Ahora |
|---|---|---|
| editorCursor.foreground | #0F5838 | #1F3838 |
| terminal.background | #E0D5C8 | #DCD0C4 |
| terminal.ansiBlue | #0050A0 | #3068C0 |
| terminal.ansiGreen | #0F5838 | #1F9058 |
| terminal.ansiRed | #B02020 | #C04020 |
| terminal.ansiYellow | #705000 | #B07818 |
| terminal.ansiCyan | #006090 | #1F7888 |
| terminal.ansiMagenta | #A04010 | #8830A0 |
| selection.background | #88B098 | #98A8B8 |
| terminal.findMatchBackground | #FFE070 | #D4B580 |
| button.background | #0F5838 | #8C7C70 |
| button.primaryBackground | #0F5838 | #C06820 |

HC Light ahora 100% alineado con la paleta de Light theme. Tratamiento de alto contraste mantenido en bordes/foco.

## [0.56.0] - 2026-07-11

### Cambiado (HC Light - Acorde con Light theme)

HC Light ahora usa el mismo fondo warm taupe que Light theme.

Fondos alineados con Light theme:

| Elemento | Antes (cream) | Ahora (taupe) |
|---|---|---|
| editor.background | #FAF6F0 | #E0D5C8 |
| sideBar.background | #F0EAD8 | #D8CCC0 |
| activityBar.background | #F0EAD8 | #D8CCC0 |
| panel.background | #F0EAD8 | #D8CCC0 |
| statusBar.background | #FAF6F0 | #FFFFFF |
| titleBar.activeBackground | #FAF6F0 | #FFFFFF |
| tab.activeBackground | #FAF6F0 | #E5DCD0 |

Foreground alineado:

| Token | Antes | Ahora |
|---|---|---|
| editor.foreground | #0F1818 | #1F3838 |
| foreground | #0F1818 | #1F3838 |
| Semantic variable | #0F1818 | #1F3838 |
| Semantic parameter | #0F1818 | #1F3838 |

Fondos de seleccion mas visibles en taupe:

| Elemento | Antes | Ahora |
|---|---|---|
| editor.selectionBackground | #C8E0D0 | #88B098 |
| editor.findMatchBackground | #C8C0B0 | #FFE070 |
| editor.wordHighlightBackground | #1F2A35 | #D8C8A0 |
| editor.lineHighlightBackground | #1A202A | #E0D5C8 |

## [0.55.0] - 2026-07-11

### Anadido (Venture Codex High Contrast Light - Nuevo tema)

Nuevo tema: Venture Codex High Contrast Light.

Basado en el Light theme (warm taupe) con tratamiento de alto contraste (WCAG AAA, bordes visibles).

Inicialmente: Fondo #FAF6F0 (cream claro), Foreground #0F1818 (teal oscuro).

Paleta HC Light inicial:

| Elemento | Color | Contraste vs fondo |
|---|---|---|
| Background | #FAF6F0 | - |
| Foreground | #0F1818 | 15.6:1 AAA |
| Mint (keywords) | #0F5838 | 8.7:1 AAA |
| Navy (functions) | #0050A0 | 8.5:1 AAA |
| Cyan (HTML/links) | #006090 | 8.1:1 AAA |
| Gold (strings) | #705000 | 7.8:1 AAA |
| Orange (properties) | #A04010 | 5.9:1 AA |
| Red (errors) | #B02020 | 6.8:1 AA |
| Amber (warnings) | #8A4818 | 6.8:1 AA |
| Warm (comments) | #5A5040 | 8.2:1 AAA |

Cobertura completa: ~460 colores, 115 tokenColors, 35 semanticTokenColors.

## [0.54.0] - 2026-07-11

### Cambiado (High Contrast theme - Auditoria Completa de Tokens)

Aplicada Opcion C del plan de auditoria: limpieza de redundancias + nuevos tokens relevantes.

Fase 1: Diferenciar Markdown markup
- Markup - Bold-Italic: #7BD0E8 a #B0F0C8 (mint para enfasis)
- Markup - Quote: agregado #A0A8B5 (antes solo italic)

Fase 2: Diferenciar TS modifiers
- TS Access Modifier: #FF7310 a #FFB060
- TS Readonly Modifier: #FF7310 a #FFE070
- TS Enum Member: #FF7310 a #FFE070

Fase 3: Eliminar JSON Key Level 2-8 redundantes (7 reglas menos)

Fase 4: Agregar 11 tokens relevantes
- Labels, Macros, Inherited Class, Module Support, Variable Annotation, Inline Code, Diff Inserted/Deleted/Changed, Constant Property, Placeholder

115 tokenColors totales (antes 122, -7 redundantes + 11 nuevos).

## [0.53.0] - 2026-07-11

### Cambiado (Light theme - Division Multi-Color de Azul - Adios Windows 95)

Se detecto que #3068C0 se veia tipo Windows 95. Aplicada la opcion D: dividir en 3 colores distintos.

Multi-color split:

| Token | Antes | Ahora | Grupo |
|---|---|---|---|
| Function Name Declaration | #3068C0 | #2C58A0 | lapis refinado |
| Support Type | #3068C0 | #2C58A0 | lapis refinado |
| CSS Classes | #3068C0 | #2C58A0 | lapis refinado |
| Python Type Hint | #3068C0 | #2C58A0 | lapis refinado |
| HTML Attributes | #3068C0 | #1F7888 | teal alineado |
| Markdown - Heading | #3068C0 | #1F7888 | teal alineado |
| CSS At-Rule | #3068C0 | #1F7888 | teal alineado |
| Attributes | #3068C0 | #C06820 | naranja (distinto) |

#3068C0 eliminado completamente de tokenColors. 3 colores distintos donde habia 1 monotono.

## [0.52.0] - 2026-07-11

### Cambiado (Light theme - Paleta ANSI de Terminal Alineada)

Aplicada opcion del plan de alineacion del ANSI terminal con main palette.

| Color | Antes | Ahora | Coincide con |
|---|---|---|---|
| terminal.ansiGreen | #8C7C70 | #1F9058 | keywords |
| terminal.ansiBrightGreen | #8C5A2B | #3A8050 | forest brillante |
| terminal.ansiMagenta | #3068C0 | #8830A0 | purpura mistico |
| terminal.ansiCyan | #006070 | #1F7888 | teal alineado |
| terminal.ansiRed | #B02828 | #C04020 | numbers |

ANSI magenta y cyan ahora distintos de blue. Bright green mas verde real.

## [0.51.0] - 2026-07-11

### Cambiado (Light theme - Fondos de input mas sutiles - Menos fatiga visual)

Se detecto que #F0EAD8 era demasiado claro, causaba fatiga visual.

Fondos cambiados de #F0EAD8 a #E0D5C8 (coincide con editor bg, sutil).

Delta de luminosidad vs panel: 8% (vs 25% antes).

## [0.50.0] - 2026-07-11

### Cambiado (Light theme - Fondos de input mas claros)

Fondos cambiados de #D8CCC0 a #F0EAD8:

- input.background
- inputBox.background
- extensions.searchInputBackground
- settings.textInputBackground
- settings.numberInputBackground
- comment.input.background
- searchEditor.textInputBackground

Inputs ahora son raised contra el panel.

## [0.49.0] - 2026-07-11

### Cambiado (Light theme - Fix de visibilidad de borde de input)

Inputs tenian border = bg (mismo color), haciendolos invisibles.

Bordes visibles:

- input.border
- inputBox.border
- extensions.searchInputBorder
- settings.textInputBorder
- settings.numberInputBorder
- comment.input.border
- searchEditor.textInputBorder

Cambiados a #A8957A (warm tan visible).

## [0.48.0] - 2026-07-11

### Cambiado (Light theme - list.focusBackground a warm taupe)

list.focusBackground en #C8A888 (bronce) afectaba el boton "More Info" en notificaciones (heredaba de list focus).

list.focusBackground cambio de #C8A888 a #D8CCC0 (warm taupe sutil).

Distincion activa vs focus:

- list.activeSelectionBackground = #C8A888 (mouse click, bronce - file selector)
- list.focusBackground = #D8CCC0 (keyboard focus, warm taupe - sutil)

## [0.47.0] - 2026-07-11

### Cambiado (Light theme - Override de boton de notificacion)

El file selector se veia bien con bronce #C8A888, pero las notificaciones tenian el boton "More Info" con el mismo bronce (heredaba de list.activeSelectionBackground).

Agregados 4 claves explicitas para notification buttons:

| Clave | Color |
|---|---|
| notification.button.background | #D8CCC0 |
| notification.button.foreground | #1F3838 |
| notification.button.hoverBackground | #C8BCB0 |
| notification.button.border | #D8CCC0 |

## [0.46.0] - 2026-07-11

### Cambiado (Light theme - Seleccion bronze mas clara - Fix visibilidad de iconos)

Se detecto que los iconos no se ven en file selector. #A08868 (bronce oscuro) hacia que los iconos no se distinguieran.

Cambiado de #A08868 a #C8A888 (bronce mas claro):

- editor.focusedStackFrameHighlightBackground
- editor.snippetFinalTabstopHighlightBackground
- selection.background
- list.activeSelectionBackground
- list.focusBackground
- menu.selectionBackground
- checkbox.selectBackground
- peekViewEditor.matchHighlightBackground
- peekViewResult.matchHighlightBackground
- peekViewResult.selectionBackground
- terminal.selectionBackground

Luminosidad +15% para visibilidad de iconos.

## [0.45.0] - 2026-07-11

### Cambiado (Light theme - Seleccion bronce - Tesoro - Aberracion removida)

Se detecto que #5A80A0 (azul cool saturado) era aberracion y no quedaba bien.

Cambiado de #5A80A0 a #A08868 (bronce sutil):

Aplicado a 11 instancias (file selector, list selections, menu, terminal, peek views).

Hue 30 (bronce/naranja calido) atado a paleta warm treasure. Contraste 2.50:1 vs fondo.

## [0.44.0] - 2026-07-11

### Cambiado (Light theme - Seleccion azul cool saturada)

Se detecto que #98A8B8 (azul-gris cool sutil) no quedaba bien.

Cambiado de #98A8B8 a #5A80A0 (azul cool saturado):

Saturacion 30% (vs 18%), Luminosidad 49%. Hue 207 (azul). Contraste 3.02:1 vs fondo.

## [0.43.0] - 2026-07-11

### Cambiado (Light theme - Seleccion azul-gris cool)

Cambiado de #C8B890 a #98A8B8 (azul-gris cool).

Aplicado a 11 instancias. Hue 210 (azul claro). Luminosidad 65%. Contraste 1.77:1 vs fondo.

## [0.42.0] - 2026-07-11

### Cambiado (Light theme - Revertir selecciones a C8B890)

Vuelto a #C8B890 (warm cream) para file selector cuando se hace click.

Mantenido editor.wordHighlightTextBackground como #B5A580 (warm tan sutil, no naranja feo).

## [0.41.0] - 2026-07-11

### Cambiado (Light theme - Seleccion bronce - Fix Sage y Naranja highlight)

Se detecto que #98B0A0 (sage verde) era horrible.

Cambiado de #98B0A0 a #A89880 (warm tan neutral).

editor.wordHighlightTextBackground cambio de #C06820 a #B5A580 (warm tan sutil, no naranja feo).

## [0.40.0] - 2026-07-11

### Cambiado (Light theme - Seleccion verde sage - Caracter de bosque)

Cambiado de #C8B890 a #98B0A0 (sage sutil).

Hue 148 (sage verde). Luminosidad 64%. Contraste 1.85:1 vs fondo.

## [0.39.0] - 2026-07-11

### Cambiado (Light theme - Limpieza de colores de notificacion y seleccion)

Se detecto que #A8957A (warm tan feo) y #E5D5A8 (amarillo claro feo).

Fase 1: Reemplazar #E5D5A8 con #E5DCD0 (warm cream sutil)

Fase 2: Reemplazar #A8957A con #C8B890 (warm taupe cream)

Consistencia resultante:

| Elemento | Antes | Ahora |
|---|---|---|
| Panel bg | #D8CCC0 | #D8CCC0 (mantener) |
| Input bg | #E5DCD0 | #E5DCD0 (mantener) |
| Notification body | #E5DCD0 | #E5DCD0 (mantener) |
| Headers | #E5D5A8 amarillo | #E5DCD0 (coincide) |
| Botones secundarios | #D8CCC0 | #D8CCC0 (mantener) |
| Selecciones | #A8957A harsh | #C8B890 (coincide) |

## [0.38.0] - 2026-07-11

### Cambiado (Light theme - Variables teal oscuro - Caracter aventura)

Se detecto que #1F1F2A (dark slate) se veia "muerto", no encajaba con aventura.

Cambiado de #1F1F2A a #1F3838 (dark teal, mantiene caracter).

Dark teal evoca "agua/mistico/bosque de noche" - aventura.

## [0.37.0] - 2026-07-11

### Cambiado (Light theme - Impulso de brillo real)

Se detecto que los colores de sintaxis se veian un poco muertos y similares.

Fase 1: Impulso de saturacion (8 colores)

| Color | Antes (v0.36) | Ahora (v0.37) | Saturacion |
|---|---|---|---|
| Mint | #1A9058 | #1F9058 | 67% |
| Gold | #A87018 | #B07818 | 80% |
| Ren v2 | #B86020 | #C06820 | 70% |
| Lapis | #2C58A0 | #3068C0 | 55% |
| Cyan | #1F7888 | #1F7888 | mantener |
| Orange | #A04010 | #C04020 | 75% |
| Amber | #8A4818 | #8A4818 | mantener |
| Comments | #7A5A50 | #8C7C70 | 21% |

Saturacion +10-15% general. Mas vibrante, mejor jerarquia.

## [0.36.0] - 2026-07-11

### Cambiado (Light theme - Impulso de brillo)

Se detecto que los colores no evocaban aventura.

Fase 1: Impulso de saturacion (8 colores) manteniendo hue y luminosidad.

| Color | Antes | Ahora | HSL |
|---|---|---|---|
| Mint | #1A8050 | #1A9058 | 142, 67%, 30% |
| Gold | #A87018 | #A87018 | mantener |
| Ren v2 | #A04010 | #B86020 | 23, 70%, 42% |
| Lapis | #0050A0 | #2C58A0 | 213, 60%, 40% |
| Cyan | #006090 | #1F7888 | 200, 100%, 28% |
| Orange | #A04010 | #C04020 | 12, 75%, 39% |
| Amber | #8A4818 | #8A4818 | mantener |
| Comments | #5A5040 | #7A5A50 | 22, 21%, 40% |

Fase 2: Variables fg mas clara

#0F1818 a #1F1F2A (dark slate, mas visible).

## [0.35.0] - 2026-07-11

### Cambiado (Light theme - Impulso de vibrancia + diferenciacion de colores)

Fase 1: Impulso de saturacion (8 colores)

Fase 2: Diferenciar bronce de gold

Fase 3: Eliminar JSON Key Level 2-8 redundantes

Fase 4: Agregar 11 tokens relevantes

## [0.34.0] - 2026-07-11

### Cambiado (Light theme - Eliminacion de pasteles)

Fase 1: Reemplazar pasteles verdes con warm taupe cream

Fase 2: Find match menos agresivo (amarillo a warm gold)

Fase 3: Diferenciar punctuation, operators, comments

Fase 4: Visibilidad de inputs

## [0.33.0] - 2026-07-11

### Corregido (Light theme - Distincion de Prisma)

Prisma.PrismaClientKnownRequestError - ambos Property Access y Class, Support Type mismo color. Diferenciados:

- Property Access = #FF6B0F (naranja)
- Class, Support Type (bold) = #B0F0C8 (mint)

## [0.32.0] - 2026-07-11

### Cambiado (Light theme - Variedad de sintaxis - Diferenciacion)

Sintaxis mejor diferenciada:

| Token | Color | Estilo |
|---|---|---|
| Function calls | #1F9058 | bold |
| Function decl | #2C58A0 | bold |
| Class/Type | #1F9058 | bold |
| Properties | #B86020 | regular |
| Method decl | #0050A0 | regular |
| Sub-methods | #5A5040 | italic |
| Comments | #8C7C70 | italic |
| Punctuation | #D8DCD0 | regular |
| Operators | #5A5040 | regular |
| Class Support Type (bold) | #1F9058 | bold |

## [0.31.0] - 2026-07-11

### Corregido (Light theme - Colores de seleccion)

El #C8B890 (warm cream) seguia siendo feo en selecciones y botones.

Fase 1: Reemplazo masivo #C8B890 a #A89880 (warm tan neutral) - 11 instancias

Fase 2: editor.wordHighlightTextBackground cambio de #C06820 a #B5A580 (warm tan sutil)

Mantenido: list.focusBackground cambio a #D8CCC0 (warm taupe sutil, no bronce).

## Resumen

Venture Codex es un tema VS Code con 4 variantes coordinadas:

- **Venture Codex Dark** - principal, acentos hexadicos vividos sobre fondo verde-cian profundo
- **Venture Codex Light** - fondo warm taupe, acentos oscuros vividos
- **Venture Codex High Contrast Dark** - WCAG AAA, dark
- **Venture Codex High Contrast Light** - WCAG AAA, warm taupe

Caracteristicas principales:
- 6 acentos elementales distribuidos hexadicamente
- Separacion semantica de roles (declaraciones vs referencias en uso)
- Cobertura completa del editor, workbench, terminal y tokens semanticos
- Resaltados especificos por lenguaje para TS, CSS, Python, Markdown, JSON/YAML
- WCAG AA+ en todos los tokens de sintaxis, AAA en variantes de alto contraste