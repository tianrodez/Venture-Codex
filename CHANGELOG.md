# Changelog

All notable changes to Venture Codex will be documented in this file.

## [0.58.2] - 2026-07-24

Package name changed to `venture-codex-theme` to avoid conflict with previous attempt to publish. Updated `package.json` with new name, displayName, homepage, and repository URL.

## [0.58.1] - 2026-07-11

### Changed (HC Light - Sticky Scroll colors fixed)

Se detectó que el sticky scroll (función header al scrollear) tenía fondo oscuro que no tenía sentido en HC Light.

Sticky scroll colors alineados con Light theme:

| Key | Antes (HC Dark leak) | Ahora (Light aligned) |
|---|---|---|
| `editorStickyScroll.background` | `#0F1818` (dark teal) | `#D8CCC0` (warm taupe) |
| `editorStickyScroll.headerBackground` | `#1B2025` (dark) | `#D8CCC0` (warm taupe) |
| `editorStickyScrollHover.background` | `#E0D8C8` | `#D8CCC0` |
| `sideBarStickyScroll.shadow` | `#00000080` | `#00000050` |
| `panelStickyScroll.shadow` | `#00000080` | `#00000040` |
| `terminalStickyScrollHover.background` | `#E0D8C8` | `#D8CCC0` |

Causa: estos colores habían quedado con valores de HC Dark por el reemplazo masivo inicial del tema HC Light. Ahora corregidos.

## [0.58.0] - 2026-07-11

### Changed (Rename High Contrast to High Contrast Dark)

Fix en el nombre del high contrast dark, agregarle el dark.

- Archivo: themes/venture-codex-high-contrast.json
  - name: Venture Codex High Contrast a Venture Codex High Contrast Dark
- Archivo: package.json
  - Theme label: Venture Codex High Contrast a Venture Codex High Contrast Dark

Ahora los 4 themes tienen nombres consistentes:

- Venture Codex Dark (vs-dark)
- Venture Codex Light (vs)
- Venture Codex High Contrast Dark (hc-black) - renombrado
- Venture Codex High Contrast Light (hc-light)

## [0.57.5] - 2026-07-11

### Changed (HC Light - Input backgrounds menos light, alineados con Light)

`#FFFFFF` para backgrounds de inputs/widgets era demasiado light, causaba eye-strain.

15 keys actualizadas de `#FFFFFF` (demasiado light) a colores de Light theme:

| Element | Antes | Ahora | Light theme |
|---|---|---|---|
| `input.background` | `#FFFFFF` | `#E0D5C8` | matches |
| `inputBox.background` | `#FFFFFF` | `#E0D5C8` | matches |
| `input.border` | `#3A3838` | `#A8957A` | matches |
| `input.foreground` | `#0F1818` | `#1F3838` | matches |
| `input.placeholderForeground` | `#3A3838` | `#8C7C70` | matches |
| `editorWidget.background` | `#FFFFFF` | `#E5DCD0` | matches |
| `editorSuggestWidget.background` | `#FFFFFF` | `#E5DCD0` | matches |
| `editorHoverWidget.background` | `#FFFFFF` | `#E5DCD0` | matches |
| `inlineChatInput.background` | `#FFFFFF` | `#E5DCD0` | matches |
| `settings.dropdownBackground` | `#FFFFFF` | `#E0D5C8` | matches |
| `settings.textInputBackground` | `#FFFFFF` | `#E0D5C8` | matches |
| `settings.numberInputBackground` | `#FFFFFF` | `#E0D5C8` | matches |
| `settings.checkboxBackground` | `#FFFFFF` | `#E0D5C8` | matches |
| `inputOption.activeBackground` | `#C8E0D0` | `#B07818` | matches |
| `inputValidation.infoBackground` | `#E8DCC8` | `#D8CCC0` | matches |
| `inputValidation.errorBackground` | `#F5D8D8` | `#E8C8C0` | matches |

`#FFFFFF` mantiene su uso correcto en foreground de badges/buttons con backgrounds oscuros, igual que Light theme.

## [0.57.4] - 2026-07-11

### Changed (HC Light - Selection colors alineados con Light)

`#98A8B8` (cool blue-grey) usado para file selector selection. Light theme usa `#C8A888` (warm bronze) para el mismo rol.

Selection colors alineados con Light theme:

| Element | Antes | Ahora | Light theme |
|---|---|---|---|
| `list.activeSelectionBackground` | `#98A8B8` | `#C8A888` | matches |
| `list.focusBackground` | `#A8B8C8` | `#D8CCC0` | matches |
| `selection.background` | `#98A8B8` | `#C8A888` | matches |
| `list.activeSelectionForeground` | `#0F1818` | `#1F3838` | matches |
| `editor.selectionBackground` | `#88B098` | `#3A5A8C40` | matches (lapis alpha) |
| `terminal.selectionBackground` | `#88B098` | `#C8A888` | matches |
| `editor.findMatchBackground` | `#FFE070` | `#D4B580` | matches |

## [0.57.3] - 2026-07-11

### Changed (HC Light - Remover #1F9058 de chrome elements)

`#1F9058` (forest green de syntax) estaba siendo usado también para chrome elements como borders, icon foregrounds, hover backgrounds. Light theme usa gold `#B07818` o orange `#C06820` para esos elementos.

164 keys actualizadas - cada una mapeada al color correspondiente de Light theme:

- Borders (focusBorder, brackets) → `#D8CCC0` o `#B07818`
- Icon foregrounds (class, function, method) → `#C06820` o `#8C7C70`
- Hover backgrounds (button, extensionButton) → `#A07018` o `#3A7A30`
- Decoration foregrounds (gitDecoration, etc.) → `#B07818`
- Badge backgrounds (badge, activityBarBadge) → `#B07818`
- Info icons/foreground → `#8C7C70`

`#1F9058` se mantiene solo para:
- 1 color: `terminal.ansiGreen`
- 18 tokenColors de syntax (Keyword, Storage Type, Function calls, etc.)
- 1 semanticTokenColor (`*.defaultLibrary`)

## [0.57.2] - 2026-07-11

### Changed (HC Light - Remover #1F7048 verde restante)

`#1F7048` (verde medio) aún aparecía en 8 instancias de HC Light.

8 instancias reemplazadas con el forest green de Light theme `#1F9058`:

- `textLink.activeForeground`
- `extensions.buttonHoverBackground`
- `extensionButton.prominentHoverBackground`
- `button.primaryHoverBackground`
- `editorLineNumber.activeForeground`
- `statusBarItem.prominentHoverBackground`
- `extensionButton.hoverBackground`
- `mergeEditor.conflict.handledFocused.border`

## [0.57.1] - 2026-07-11

### Changed (HC Light - Remover #0F5838 verde restante)

`#0F5838` (verde oscuro que NO existe en Light theme) aún aparecía en 155 instancias de HC Light.

155 instancias reemplazadas con el forest green de Light theme `#1F9058`:

- 137 colors section (symbolIcons, borders, activityBar, gitDecoration, notebook, testing, terminal symbols, extensions, chat, inlineEdit, markdownAlert, charts, scmGraph, comment views, panel titles, settings)
- 5 tokenColors (CSS Property Names, Markup - Bold-Italic, YAML Key, Markdown Checkbox Done)
- 1 semanticTokenColor (`*.defaultLibrary`)

## [0.57.0] - 2026-07-11

### Changed (HC Light - Alineado con colores de Light theme)

HC Light ahora usa exactamente los mismos colores que Light theme. Sin variantes oscuras - identidad visual coherente.

Token colors alineados con Light (muestra):

| Token | Antes HC Light | Ahora HC Light | Light theme |
|---|---|---|---|
| Comments | `#5A5040` | `#8C7C70` | matches |
| Variables | `#0F1818` | `#1F3838` | matches |
| Keyword (Storage Type) | `#0F5838` | `#1F9058` | matches |
| Function calls | `#A04010` | `#1F9058` | matches |
| Operators | `#5A5040` | `#A07018` | matches |
| Punctuation | `#D8DCD0` | `#5A4530` | matches |
| Function decl | `#0050A0` | `#2C58A0` | matches |
| Numbers | `#A04010` | `#C04020` | matches |
| Strings | `#705000` | `#B07818` | matches |
| Method decl | `#0050A0` | `#C06820` | matches |
| Properties | `#A04010` | `#C06820` | matches |
| Sub-methods | `#0050A0` | `#8C7C70` | matches |
| Markdown - Heading | `#006090` | `#1F7888` | matches |
| HTML Attributes | `#006090` | `#1F7888` | matches |
| CSS Classes | `#0050A0` | `#2C58A0` | matches |
| Python Type Hint | `#0050A0` | `#2C58A0` | matches |
| JSX | `#0050A0` | `#C06820` | matches |

UI Chrome alineado también (muestra):

| Element | Antes | Ahora |
|---|---|---|
| `editorCursor.foreground` | `#0F5838` | `#1F3838` |
| `terminal.background` | `#E0D5C8` | `#DCD0C4` |
| `terminal.ansiBlue` | `#0050A0` | `#3068C0` |
| `terminal.ansiGreen` | `#0F5838` | `#1F9058` |
| `terminal.ansiRed` | `#B02020` | `#C04020` |
| `terminal.ansiYellow` | `#705000` | `#B07818` |
| `terminal.ansiCyan` | `#006090` | `#1F7888` |
| `terminal.ansiMagenta` | `#A04010` | `#8830A0` |
| `selection.background` | `#88B098` | `#98A8B8` |
| `findMatchBackground` | `#FFE070` | `#D4B580` |
| `button.background` | `#0F5838` | `#8C7C70` |
| `button.primaryBackground` | `#0F5838` | `#C06820` |

HC Light ahora 100% alineado con Light theme palette. High contrast treatment mantenido en borders/focus.

## [0.56.0] - 2026-07-11

### Changed (HC Light - Acorde con Light theme)

HC Light ahora usa el mismo bg warm taupe que Light theme.

Backgrounds alineados con Light theme:

| Elemento | Antes (cream) | Ahora (taupe) |
|---|---|---|
| `editor.background` | `#FAF6F0` | `#E0D5C8` |
| `sideBar.background` | `#F0EAD8` | `#D8CCC0` |
| `activityBar.background` | `#F0EAD8` | `#D8CCC0` |
| `panel.background` | `#F0EAD8` | `#D8CCC0` |
| `statusBar.background` | `#FAF6F0` | `#FFFFFF` |
| `titleBar.activeBackground` | `#FAF6F0` | `#FFFFFF` |
| `tab.activeBackground` | `#FAF6F0` | `#E5DCD0` |

Foreground alineado:

| Token | Antes | Ahora |
|---|---|---|
| `editor.foreground` | `#0F1818` | `#1F3838` |
| `foreground` | `#0F1818` | `#1F3838` |
| Semantic variable | `#0F1818` | `#1F3838` |
| Semantic parameter | `#0F1818` | `#1F3838` |

Selection backgrounds más visibles en taupe:

| Elemento | Antes | Ahora |
|---|---|---|
| `editor.selectionBackground` | `#C8E0D0` | `#88B098` |
| `editor.findMatchBackground` | `#C8C0B0` | `#FFE070` |
| `editor.wordHighlightBackground` | `#1F2A35` | `#D8C8A0` |
| `editor.lineHighlightBackground` | `#1A202A` | `#E0D5C8` |

## [0.55.0] - 2026-07-11

### Added (Venture Codex High Contrast Light - New Theme)

Nuevo tema: Venture Codex High Contrast Light.

Basado en el Light theme (warm taupe) con tratamiento de high contrast (WCAG AAA, borders visibles).

Inicialmente: Background `#FAF6F0` (light cream), Foreground `#0F1818` (dark teal).

Paleta HC Light inicial:

| Elemento | Color | Contrast vs bg |
|---|---|---|
| Background | `#FAF6F0` | - |
| Foreground | `#0F1818` | 15.6:1 AAA |
| Mint (keywords) | `#0F5838` | 8.7:1 AAA |
| Navy (functions) | `#0050A0` | 8.5:1 AAA |
| Cyan (HTML/links) | `#006090` | 8.1:1 AAA |
| Gold (strings) | `#705000` | 7.8:1 AAA |
| Orange (properties) | `#A04010` | 5.9:1 AA |
| Red (errors) | `#B02020` | 6.8:1 AA |
| Amber (warnings) | `#8A4818` | 6.8:1 AA |
| Warm (comments) | `#5A5040` | 8.2:1 AAA |

Cobertura completa: ~460 colors, 115 tokenColors, 35 semanticTokenColors.

## [0.54.0] - 2026-07-11

### Changed (High Contrast theme - Auditoria Completa de Tokens)

Aplicada Opcion C del plan de auditoria: limpieza de redundancias + nuevos tokens relevantes.

Phase 1: Diferenciar Markdown markup
- Markup - Bold-Italic: `#7BD0E8` a `#B0F0C8` (mint para emphasis)
- Markup - Quote: agregado `#A0A8B5` (era solo italic)

Phase 2: Diferenciar TS modifiers
- TS Access Modifier: `#FF7310` a `#FFB060`
- TS Readonly Modifier: `#FF7310` a `#FFE070`
- TS Enum Member: `#FF7310` a `#FFE070`

Phase 3: Eliminar JSON Key Level 2-8 redundantes (7 reglas menos)

Phase 4: Agregar 11 tokens relevantes
- Labels, Macros, Inherited Class, Module Support, Variable Annotation, Inline Code, Diff Inserted/Deleted/Changed, Constant Property, Placeholder

115 tokenColors totales (antes 122, -7 redundantes + 11 nuevos).

## [0.53.0] - 2026-07-11

### Changed (Light theme - Multi-Color Blue Split - No More Windows 95)

Se detecto que `#3068C0` se veia tipo Windows 95. Aplicada Opcion D: dividir en 3 colores distintos.

Multi-color split:

| Token | Antes | Ahora | Grupo |
|---|---|---|---|
| Function Name Declaration | `#3068C0` | `#2C58A0` | refined lapis |
| Support Type | `#3068C0` | `#2C58A0` | refined lapis |
| CSS Classes | `#3068C0` | `#2C58A0` | refined lapis |
| Python Type Hint | `#3068C0` | `#2C58A0` | refined lapis |
| HTML Attributes | `#3068C0` | `#1F7888` | teal aligned |
| Markdown - Heading | `#3068C0` | `#1F7888` | teal aligned |
| CSS At-Rule | `#3068C0` | `#1F7888` | teal aligned |
| Attributes | `#3068C0` | `#C06820` | orange (distinct) |

`#3068C0` eliminado completamente de tokenColors. 3 colores distintos donde habia 1 monotono.

## [0.52.0] - 2026-07-11

### Changed (Light theme - ANSI Terminal Palette Aligned)

Aplicada Opcion del plan de alineacion del ANSI terminal con main palette.

| Color | Antes | Ahora | Match con |
|---|---|---|---|
| `terminal.ansiGreen` | `#8C7C70` | `#1F9058` | keywords |
| `terminal.ansiBrightGreen` | `#8C5A2B` | `#3A8050` | bright forest |
| `terminal.ansiMagenta` | `#3068C0` | `#8830A0` | mystic purple |
| `terminal.ansiCyan` | `#006070` | `#1F7888` | teal aligned |
| `terminal.ansiRed` | `#B02828` | `#C04020` | numbers |

ANSI magenta y cyan ahora distintos de blue. Bright green mas verde real.

## [0.51.0] - 2026-07-11

### Changed (Light theme - Subtler Input Backgrounds - Less Eye Strain)

Se detecto que `#F0EAD8` era demasiado claro, causaba eye strain.

Backgrounds cambiados de `#F0EAD8` a `#E0D5C8` (matches editor bg, sutil).

Lightness delta vs panel: 8% (vs 25% antes).

## [0.50.0] - 2026-07-11

### Changed (Light theme - Lighter Input Backgrounds)

Backgrounds cambiados de `#D8CCC0` a `#F0EAD8`:

- input.background
- inputBox.background
- extensions.searchInputBackground
- settings.textInputBackground
- settings.numberInputBackground
- comment.input.background
- searchEditor.textInputBackground

Inputs ahora son raised contra el panel.

## [0.49.0] - 2026-07-11

### Changed (Light theme - Input Border Visibility Fix)

Inputs tenian `border = bg` (mismo color), haciendolos invisibles.

Borders visibles:

- input.border
- inputBox.border
- extensions.searchInputBorder
- settings.textInputBorder
- settings.numberInputBorder
- comment.input.border
- searchEditor.textInputBorder

Cambiados a `#A8957A` (warm tan visible).

## [0.48.0] - 2026-07-11

### Changed (Light theme - list.focusBackground to warm taupe)

`list.focusBackground` en `#C8A888` (bronze) afectaba el "More Info" button en notifications (heredaba de list focus).

`list.focusBackground` cambio de `#C8A888` a `#D8CCC0` (warm taupe sutil).

Distincion activa vs focus:

- `list.activeSelectionBackground` = `#C8A888` (mouse click, bronze - file selector)
- `list.focusBackground` = `#D8CCC0` (keyboard focus, warm taupe - sutil)

## [0.47.0] - 2026-07-11

### Changed (Light theme - Notification Button Override)

El file selector se veia bien con bronze `#C8A888`, pero las notifications tenian el "More Info" button con el mismo bronze (heredaba de list.activeSelectionBackground).

Agregados 4 keys explicitos para notification buttons:

| Key | Color |
|---|---|
| `notification.button.background` | `#D8CCC0` |
| `notification.button.foreground` | `#1F3838` |
| `notification.button.hoverBackground` | `#C8BCB0` |
| `notification.button.border` | `#D8CCC0` |

## [0.46.0] - 2026-07-11

### Changed (Light theme - Lighter Bronze Selection - Icon Visibility Fix)

Se detecto que los iconos no se ven en file selector. `#A08868` (bronze oscuro) hacia que los iconos no se distinguieran.

Cambiado de `#A08868` a `#C8A888` (lighter bronze):

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

Lightness +15% para visibilidad de iconos.

## [0.45.0] - 2026-07-11

### Changed (Light theme - Bronze Selection - Treasure - Removed Abberation)

Se detecto que `#5A80A0` (saturated cool blue) era aberracion y no quedaba bien.

Cambiado de `#5A80A0` a `#A08868` (subtle bronze):

Aplicado a 11 instancias (file selector, list selections, menu, terminal, peek views).

Hue 30 (warm bronze/orange) ties a paleta warm treasure. Contrast 2.50:1 vs bg.

## [0.44.0] - 2026-07-11

### Changed (Light theme - Saturated Cool Blue Selection)

Se detecto que `#98A8B8` (cool blue-grey sutil) no quedaba bien.

Cambiado de `#98A8B8` a `#5A80A0` (saturated cool blue):

Saturacion 30% (vs 18%), Lightness 49%. Hue 207 (azul). Contrast 3.02:1 vs bg.

## [0.43.0] - 2026-07-11

### Changed (Light theme - Cool Blue-Grey Selection)

Cambiado de `#C8B890` a `#98A8B8` (cool blue-grey).

Aplicado a 11 instancias. Hue 210 (azul claro). Lightness 65%. Contrast 1.77:1 vs bg.

## [0.42.0] - 2026-07-11

### Changed (Light theme - Revert Selections to C8B890)

Vuelto a `#C8B890` (warm cream) para file selector cuando se clickea.

Mantenido `editor.wordHighlightTextBackground` como `#B5A580` (warm tan sutil, no orange feo).

## [0.41.0] - 2026-07-11

### Changed (Light theme - Bronze Selection - Fix Sage & Orange Highlight)

Se detecto que `#98B0A0` (sage green) era horrible.

Cambiado de `#98B0A0` a `#A89880` (warm tan neutral).

`editor.wordHighlightTextBackground` cambio de `#C06820` a `#B5A580` (warm tan sutil, no orange feo).

## [0.40.0] - 2026-07-11

### Changed (Light theme - Sage Green Selection - Forest Character)

Cambiado de `#C8B890` a `#98B0A0` (subtle sage).

Hue 148 (sage green). Lightness 64%. Contrast 1.85:1 vs bg.

## [0.39.0] - 2026-07-11

### Changed (Light theme - Notification & Selection Color Cleanup)

Se detecto que `#A8957A` (warm tan feo) y `#E5D5A8` (light yellow feo).

Phase 1: Reemplazar `#E5D5A8` con `#E5DCD0` (warm cream sutil)

Phase 2: Reemplazar `#A8957A` con `#C8B890` (warm taupe cream)

Consistencia resultante:

| Elemento | Antes | Ahora |
|---|---|---|
| Panel bg | `#D8CCC0` | `#D8CCC0` (keep) |
| Input bg | `#E5DCD0` | `#E5DCD0` (keep) |
| Notification body | `#E5DCD0` | `#E5DCD0` (keep) |
| Headers | `#E5D5A8` yellow | `#E5DCD0` (match) |
| Buttons sec | `#D8CCC0` | `#D8CCC0` (keep) |
| Selections | `#A8957A` harsh | `#C8B890` (match) |

## [0.38.0] - 2026-07-11

### Changed (Light theme - Dark Teal Variables - Adventure Character)

Se detecto que `#1F1F2A` (dark slate) se veia "muerto", no encajaba con aventura.

Cambiado de `#1F1F2A` a `#1F3838` (dark teal, mantiene character).

Dark teal evoca "agua/mystic/forest at night" - aventura.

## [0.37.0] - 2026-07-11

### Changed (Light theme - True Brightness Boost)

Se detecto que los colores de sintaxis se veian un poco muertos y similares.

Phase 1: Boost de saturacion (8 colores)

| Color | Antes (v0.36) | Ahora (v0.37) | Saturacion |
|---|---|---|---|
| Mint | `#1A9058` | `#1F9058` | 67% |
| Gold | `#A87018` | `#B07818` | 80% |
| Ren v2 | `#B86020` | `#C06820` | 70% |
| Lapis | `#2C58A0` | `#3068C0` | 55% |
| Cyan | `#1F7888` | `#1F7888` | keep |
| Orange | `#A04010` | `#C04020` | 75% |
| Amber | `#8A4818` | `#8A4818` | keep |
| Comments | `#7A5A50` | `#8C7C70` | 21% |

Saturacion +10-15% general. Mas vibrante, mejor jerarquia.

## [0.36.0] - 2026-07-11

### Changed (Light theme - Brightness Boost)

Se detecto que los colores no evocaban aventura.

Phase 1: Boost de saturacion (8 colores) manteniendo hue y lightness.

| Color | Antes | Ahora | HSL |
|---|---|---|---|
| Mint | `#1A8050` | `#1A9058` | 142, 67%, 30% |
| Gold | `#A87018` | `#A87018` | keep |
| Ren v2 | `#A04010` | `#B86020` | 23, 70%, 42% |
| Lapis | `#0050A0` | `#2C58A0` | 213, 60%, 40% |
| Cyan | `#006090` | `#1F7888` | 200, 100%, 28% |
| Orange | `#A04010` | `#C04020` | 12, 75%, 39% |
| Amber | `#8A4818` | `#8A4818` | keep |
| Comments | `#5A5040` | `#7A5A50` | 22, 21%, 40% |

Phase 2: Variables fg lighter

`#0F1818` a `#1F1F2A` (dark slate, mas visible).

## [0.35.0] - 2026-07-11

### Changed (Light theme - Vibrancy Boost + Color Differentiation)

Phase 1: Boost de saturacion (8 colores)

Phase 2: Diferenciar bronze de gold

Phase 3: Eliminar JSON Key Level 2-8 redundantes

Phase 4: Agregar 11 tokens relevantes

## [0.34.0] - 2026-07-11

### Changed (Light theme - Pastel Elimination)

Phase 1: Reemplazar pasteles verdes con warm taupe cream

Phase 2: Find match menos agresivo (yellow a warm gold)

Phase 3: Diferenciar punctuation, operators, comments

Phase 4: Input visibility

## [0.33.0] - 2026-07-11

### Fixed (Light theme - Prisma distinction)

`Prisma.PrismaClientKnownRequestError` - ambos `Property Access` y `Class, Support Type` mismo color. Diferenciados:

- Property Access = `#FF6B0F` (orange)
- Class, Support Type (bold) = `#B0F0C8` (mint)

## [0.32.0] - 2026-07-11

### Changed (Light theme - Syntax Variety - Differentiation)

Sintaxis mejor diferenciada:

| Token | Color | Style |
|---|---|---|
| Function calls | `#1F9058` | bold |
| Function decl | `#2C58A0` | bold |
| Class/Type | `#1F9058` | bold |
| Properties | `#B86020` | regular |
| Method decl | `#0050A0` | regular |
| Sub-methods | `#5A5040` | italic |
| Comments | `#8C7C70` | italic |
| Punctuation | `#D8DCD0` | regular |
| Operators | `#5A5040` | regular |
| Class Support Type (bold) | `#1F9058` | bold |

## [0.31.0] - 2026-07-11

### Fixed (Light theme - Selection colors)

El `#C8B890` (warm cream) seguia siendo feo en selections y buttons.

Phase 1: Reemplazo masivo `#C8B890` a `#A89880` (warm tan neutral) - 11 instancias

Phase 2: `editor.wordHighlightTextBackground` cambio de `#C06820` a `#B5A580` (warm tan sutil)

Mantenido: `list.focusBackground` cambio a `#D8CCC0` (warm taupe sutil, no bronze).

## Summary

Venture Codex es un tema VS Code con 4 variantes coordinadas:

- **Venture Codex Dark** - primary, vivid hexadic accents on deep green-cyan ground
- **Venture Codex Light** - warm pergamino background, vivid dark accents
- **Venture Codex High Contrast Dark** - WCAG AAA, dark
- **Venture Codex High Contrast Light** - WCAG AAA, warm taupe

Caracteristicas principales:
- 6 elemental accents hexadically distributed
- Semantic role separation (declarations vs in-use references)
- Full coverage of editor, workbench, terminal, semantic tokens
- Language-specific highlights for TS, CSS, Python, Markdown, JSON/YAML
- WCAG AA+ on all syntax tokens, AAA on high contrast variants