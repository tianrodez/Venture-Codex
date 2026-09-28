# Changelog

All notable changes to Venture Codex will be documented in this file.

## [0.59.0] - 2026-09-27

### Improved (Find match visibility)

The `Ctrl+F` find highlight was barely visible, especially on the current line: `editor.findMatchHighlightBackground` matched `selectionHighlightBackground` or the editor background itself, and in the Dark theme `editor.findMatchBorder` / `editor.findMatchHighlightBorder` were set to the editor background color (an invisible border), so the current match lost its only definition. In some files (diff editor, notebooks, selections) the matches simply disappeared.

| Theme | Current match | Other matches |
|---|---|---|
| Dark | `#3A4748` + invisible border → `#4E6063` + `#7E9599` border | `#252E30` (invisible) → `#8FA5A850` (translucent, blends with any row background) |
| Light | unchanged (`#D4B580` + `#C06820`) | `#3A5A8C30` + beige border → `#3A5A8C55` + `#3A5A8C` border; removed forced amber `findMatchHighlightForeground` |
| HC Dark | unchanged (`#3A4748` + `#FFE070`) | opaque `#A0A8B5` (unreadable text) → `#A0A8B560` translucent + solid `#FFE070` border |
| HC Light | `#D4B580` + `#705000` | was identical to current match → softer `#E8D8B0` + same `#705000` border (current vs. other now distinguishable) |

The same values were mirrored in `terminal.findMatch*` in all four themes, which also fixes HC Light's near-black `#3A3838` terminal other-match block. Minimap and overview ruler find marks were left unchanged (they were already high-visibility).

## [0.58.5] - 2026-07-25

### Fixed (Button hover color)

In Dark and High Contrast Dark themes, `button.hoverBackground` was set to washed-out sage green (`#A8C893` / `#C0E8A5`) that did not match the theme's saturated palette and was lighter than the button background, producing the inverse of the intended hover effect.

| Theme | Before | After |
|---|---|---|
| Dark | `#A8C893` (desaturated sage) | `#76C997` (darker mint, indicates hover) |
| HC Dark | `#C0E8A5` (light sage) | `#9DD9A0` (darker mint, indicates hover) |

The new colors are darker variants of the theme's mint accent, making the hover state clearly distinguishable from the default background. Light and HC Light themes were already correct (hover darker than background).

## [0.58.4] - 2026-07-25

### Fixed (Python Docstring)

The `String Template` rule in Python was overriding docstrings (`"""..."""`), making them appear as regular strings instead of documentation. Added a dedicated `Python Docstring` rule in all 4 themes to color docstrings (and their `"""` / `'''` delimiters) like comments, with italic style.

| Theme | Docstring color | Style |
|---|---|---|
| Dark | `#94A89C` (sage) | italic |
| Light | `#8C7C70` (warm soft) | italic |
| HC Dark | `#A0A8B5` (grey) | italic |
| HC Light | `#8C7C70` (warm soft) | italic |

### Fixed (Python Function Parameter)

The `Function Parameter` rule used sage/grey colors that looked like comments. In Dark theme the color was `#9CA898` (same as `Comments`). The parameters now use **Ren Sword v2 orange** (`#FF6B0F` Dark, `#C06820` Light, `#FF7050` HC Dark, `#C06820` HC Light) with italic style, and the scope is restricted to Python only:

```
source.python variable.parameter.function
```

This means only Python function parameters get the orange color; other languages (JS, TS, C#, etc.) keep their default parameter coloring.

### Fixed (Python Logical Keywords)

Python keywords `and`, `or`, `not`, `in`, `is` were being matched by the `Operators` rule (slate/grey color, same family as comments). They are now in the `Keyword` rule, so they render in the keyword color (mint in Dark, forest in Light).

The `Operators` rule no longer includes the general `keyword.operator.logical` scope. Instead, Python-specific scopes were added to `Keyword`:

- `keyword.operator.logical.python` (`and`, `or`, `not`)
- `keyword.operator.word.python` (`in`, `is`, `not`)

## [0.58.3] - 2026-07-24

### Fixed (String Template color)

The `String Template` rule used the foreground color (white / dark teal) instead of the gold color used for regular strings. This caused template literals (backticks) to appear in white instead of gold like other strings.

Fixed in all 4 themes:

| Theme | Before | After |
|---|---|---|
| Dark | `#F0F0F5` (white) | `#FFE055` (gold) |
| Light | `#1F3838` (dark teal) | `#B07818` (gold) |
| HC Dark | `#FFFFFF` (white) | `#FFE070` (gold) |
| HC Light | `#0F1818` (dark teal) | `#B07818` (gold) |

### Fixed (HTML Native Tag scope)

The `HTML Native Tag` rule used `meta.tag.tsx` and `meta.tag.jsx` as scopes, which were too broad — they applied to ALL content inside a tag, including text between `<label>` and `</label>`. This caused text inside JSX tags to appear in mint as if it were a tag.

Removed `meta.tag.tsx` and `meta.tag.jsx` from the scopes. Now only specific tag-name scopes are used:

- `entity.name.tag.html`
- `entity.name.tag.match.html`
- `meta.tag.sgml`
- `meta.tag.sgml.html`
- `entity.name.tag.tsx`
- `entity.name.tag.jsx`

## [0.58.2] - 2026-07-24

Package name changed to `venture-codex-theme` to avoid conflict with previous attempt to publish. Updated `package.json` with new name, displayName, homepage, and repository URL.

## [0.58.1] - 2026-07-11

### Changed (HC Light - Sticky Scroll colors fixed)

Detected that the sticky scroll (function header when scrolling) had a dark background that made no sense in HC Light.

Sticky scroll colors aligned with Light theme:

| Key | Before (HC Dark leak) | After (Light aligned) |
|---|---|---|
| `editorStickyScroll.background` | `#0F1818` (dark teal) | `#D8CCC0` (warm taupe) |
| `editorStickyScroll.headerBackground` | `#1B2025` (dark) | `#D8CCC0` (warm taupe) |
| `editorStickyScrollHover.background` | `#E0D8C8` | `#D8CCC0` |
| `sideBarStickyScroll.shadow` | `#00000080` | `#00000050` |
| `panelStickyScroll.shadow` | `#00000080` | `#00000040` |
| `terminalStickyScrollHover.background` | `#E0D8C8` | `#D8CCC0` |
