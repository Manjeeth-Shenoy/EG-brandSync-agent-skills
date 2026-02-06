# EG BrandSync Agent Skills

Claude Code agent skills for the EG BrandSync design system.

## Available Skills

### brandsync-design-system

Gives AI agents full knowledge of the EG BrandSync design system — color tokens, semantic mappings, typography scales, and WCAG accessibility data.

**Install:**

```bash
npx skills add Manjeeth-Shenoy/EG-brandSync-agent-skills --skill brandsync-design-system
```

**What's included:**

- 14 brand color palettes with full shade scales (50–950)
- Semantic token mappings for light and dark mode
- WCAG AA/AAA compliance data for all color combinations
- Responsive typography scales (Desktop, Tablet, Mobile)
- Export generators for CSS, SCSS, JSON, and JavaScript

**Parameterized:** Pass a color name as an argument to focus on a specific brand palette:

```
purple, cobalt, blue, steel, teal, jade, green, lime, yellow, amber, orange, magenta, maroon, violet
```
