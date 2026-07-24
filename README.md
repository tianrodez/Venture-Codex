<div align="center">
  <img src="./theme-img/venture-codex-logo.png" alt="Venture Codex Logo" width="256">
</div>

# Venture Codex

Open the codex. Light the lantern. The adventure starts on line 1.

Venture Codex is a vivid VS Code theme built for developers who spend more hours inside the editor than outside it. Every keyword, every function, every glyph is colored like a page from an illuminated manuscript: distinct, readable, made to be lived in. Whether you're chasing a bug at 2 a.m. or shipping a feature on a Monday morning, your eyes should not have to fight your code.

Four coordinated variants share the same color identity:

- **Venture Codex Dark** — primary variant, vivid hexadic accents on a deep green-cyan ground.
- **Venture Codex Light** — warm background, vivid dark accents tuned for daylight.
- **Venture Codex High Contrast Dark** — WCAG-AAA-friendly, for accessibility and projector use.
- **Venture Codex High Contrast Light** — WCAG-AAA-friendly, warm background with vivid dark accents.

## Theme Preview

### Venture Codex Dark

<p align="center">
  <img src="./theme-img/venture-codex-dark.png" alt="Venture Codex Dark Preview" width="720">
</p>

### Venture Codex Light

<p align="center">
  <img src="./theme-img/venture-codex-light.png" alt="Venture Codex Light Preview" width="720">
</p>

### Venture Codex High Contrast Dark

<p align="center">
  <img src="./theme-img/venture-codex-high-contrast-dark.png" alt="Venture Codex High Contrast Dark Preview" width="720">
</p>

### Venture Codex High Contrast Light

<p align="center">
  <img src="./theme-img/venture-codex-high-contrast-light.png" alt="Venture Codex High Contrast Light Preview" width="720">
</p>

## Installation

### From VS Code Marketplace

1. Open **Extensions** (`Ctrl+Shift+X` / `Cmd+Shift+X`).
2. Search for `Venture Codex`.
3. Click **Install**.
4. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and run **Preferences: Color Theme**.
5. Choose one of:
   - `Venture Codex Dark`
   - `Venture Codex Light`
   - `Venture Codex High Contrast Dark`
   - `Venture Codex High Contrast Light`

## Recommended settings

For the best visual experience, pair with a ligature-aware font, enable bracket pair colorization, and tune the cursor:

```jsonc
// settings.json
{
  "editor.fontFamily": "Cascadia Code, Fira Code, JetBrains Mono",
  "editor.fontLigatures": true,
  "editor.cursorBlinking": "smooth",
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.semanticHighlighting.enabled": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.bracketPairColorization.independentColorPoolPerBracketType": true,
  "editor.guides.bracketPairs": "active",
  "workbench.colorTheme": "Venture Codex Dark"
}
```

## Accessibility

All four variants are tuned for WCAG AA or better on syntax tokens against their respective backgrounds.

## Contributing

Contributions are welcome. To propose changes:

1. Check WCAG contrast for any new or changed colors against the relevant background.
2. Open a pull request with a clear description and, if applicable, screenshots.

When proposing color changes:

- Prefer adjusting existing palette values over introducing new colors.
- Preserve the role separation across variants (Dark, Light, HC Dark, HC Light) so the four themes feel like one family.
- Keep this README and `CHANGELOG.md` updated with any user-facing change.

## License

MIT — see [LICENSE](./LICENSE).