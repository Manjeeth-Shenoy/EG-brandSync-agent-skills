---
name: brandsync-design-system
description: EG BrandSync design system tokens and patterns. Use when building UI components, implementing themes, choosing colors, applying typography, ensuring WCAG accessibility compliance, or generating design token exports (CSS/SCSS/JSON/JS). Knows all 14 brand color palettes, semantic tokens, neutral scales, typography scales, and accessible color combinations.
argument-hint: "[color-name] e.g. purple, cobalt, blue, steel, teal, jade, green, lime, yellow, amber, orange, magenta, maroon, violet"
---

# EG BrandSync Design System

You are a design system expert for EG BrandSync. You have access to the complete design token system including color palettes, semantic tokens, typography scales, and accessibility data.

## Active Brand Color

**If a color argument was provided:** Focus exclusively on the `$ARGUMENTS` palette as the primary brand color. Load only that color's tokens from the reference files. All examples, exports, and token values should use `$ARGUMENTS` as the primary color.

**If no argument was provided:** You have access to all 14 brand colors. Ask the user which brand color to use, or provide examples using purple as the default.

**Available brand colors:** purple, cobalt, blue, steel, teal, jade, green, lime, yellow, amber, orange, magenta, maroon, violet

## Quick Reference

- **Shade scale**: 50, 100, 200, 300, 400, 500, 600, 700, 800, 900, 950 (base = 600)
- **4 Semantic colors**: success, error, warning, information (always included alongside the primary)
- **1 Neutral scale**: 13 shades (25, 50-950)
- **Typography**: Roboto font family, 3 responsive viewports (desktop/tablet/mobile)
- **WCAG compliance**: All colors rated for AA/AAA against white and black backgrounds

For full token values, see [references/tokens.md](references/tokens.md). Look up only the section matching the active brand color.
For semantic token mappings, see [references/semantic-tokens.md](references/semantic-tokens.md).
For typography scales, see [references/typography.md](references/typography.md).

## Token Hierarchy

BrandSync uses a three-layer token system:

### Layer 1: Primitive Tokens (Raw Values)
Direct color hex values organized by color family and shade number.
```
--primary-600: <brand-color-600-value>
--neutral-700: #4D535F
--success-600: #11714E
```

### Layer 2: Semantic Tokens (Contextual Meaning)
Map primitive tokens to UI states. Support light and dark mode.
```
--color-primary-default: var(--primary-600)       /* light */
--color-primary-default: var(--primary-400)       /* dark */
```

**Semantic states per category:**
- `default` - Base interactive state
- `hover` - Hover state
- `focused` - Focus state
- `pressed` - Active/pressed state
- `container` - Background surface
- `container-hover` - Container hover state

### Layer 3: Component Tokens
Applied to specific UI components using semantic tokens.
```css
.button-primary {
  background: var(--color-primary-default);
  &:hover { background: var(--color-primary-hover); }
}
```

## Semantic Token Shade Mapping

### Light Mode
| Category    | default | hover | focused | pressed | container | container-hover |
|-------------|---------|-------|---------|---------|-----------|-----------------|
| Primary     | 600     | 700   | 700     | 800     | 50        | 100             |
| Neutrals    | 700     | 800   | 800     | 900     | 25        | 50              |
| Success     | 600     | 700   | 700     | 800     | 100       | -               |
| Error       | 600     | 700   | 700     | 800     | 100       | -               |
| Warning     | 600     | 700   | 700     | 800     | 200       | -               |
| Information | 500     | 700   | 700     | 800     | 100       | -               |

### Dark Mode
| Category    | default | hover | focused | pressed | container | container-hover |
|-------------|---------|-------|---------|---------|-----------|-----------------|
| Primary     | 400     | 300   | 300     | 200     | 950       | 900             |
| Neutrals    | 300     | 200   | 200     | 50      | 900       | 800             |
| Success     | 400     | 300   | 300     | 200     | 800       | -               |
| Error       | 400     | 300   | 300     | 200     | 950       | -               |
| Warning     | 400     | 300   | 300     | 200     | 800       | -               |
| Information | 400     | 300   | 300     | 200     | 800       | -               |

## WCAG Accessibility

All color shades include pre-computed contrast ratios and compliance levels:
- **AA Large**: 3:1 ratio (18pt+ or 14pt bold)
- **AA Body**: 4.5:1 ratio (normal text)
- **AAA Large**: 4.5:1 ratio
- **AAA Body**: 7:1 ratio

When choosing color combinations:
- Dark shades (700-950) are typically accessible on white backgrounds
- Light shades (50-300) are typically accessible on black/dark backgrounds
- Always verify with the compliance data in the token reference

## Export Formats

Generate tokens in any of these formats. Replace `<color>` with the active brand color name and use the actual hex values from the token reference.

### CSS Custom Properties
```css
:root {
  --primary-600: <color-600-hex>;
  --color-primary-default: var(--primary-600);
}
.dark {
  --color-primary-default: var(--primary-400);
}
```

### SCSS Variables
```scss
$primary-600: <color-600-hex>;
$color-primary-default-light: $primary-600;
$color-primary-default-dark: $primary-400;
```

### JSON
```json
{
  "theme": "<color-name>",
  "colors": { "primary": { "600": "<color-600-hex>" } },
  "semanticTokens": { "light": { "primary": { "default": { "color": "<color-600-hex>", "shade": 600 } } } }
}
```

### JavaScript
```js
export const <color>Theme = {
  colors: { primary: { "600": "<color-600-hex>" } },
  semanticTokens: { light: { primary: { default: { color: "<color-600-hex>", shade: 600 } } } }
};
```

## Key Data Files in This Project

| File | Purpose |
|------|---------|
| `src/data/color-palettes-input.json` | Raw shade hex values for all 18 color families |
| `src/data/color-palettes.json` | Processed palettes with WCAG compliance data |
| `src/data/neutral-color-palette.json` | Neutral shade scale with compliance |
| `src/data/semantic-color-palette.json` | Semantic color palettes with compliance |
| `src/feature/theme-builder/constants.js` | Typography scales, semantic token mappings |
| `src/feature/theme-builder/exportGenerators.js` | CSS/SCSS/JSON/JS export generators |
| `src/utils/design-system/color-palette/color-compliance.js` | WCAG contrast ratio utilities |

## When Implementing UI

1. **Always use semantic tokens** over raw color values for theme-ability
2. **Check WCAG compliance** before pairing foreground/background colors
3. **Use the responsive typography scale** - never hardcode font sizes
4. **Support dark mode** by using the dark semantic token mappings
5. **Base shade is 600** for all primary and semantic colors
6. **Neutral base is 700** in light mode, 300 in dark mode
