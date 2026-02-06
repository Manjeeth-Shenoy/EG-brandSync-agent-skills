# BrandSync Typography Scale Reference

Font family: **Roboto** (all styles)

The typography system is responsive across 3 viewports:
- **Desktop**: Default/base
- **Tablet**: max-width 1023px
- **Mobile**: max-width 767px

## Display Styles

Bold weight. Used for hero sections, landing pages, large headlines.

| Style | Desktop | Tablet | Mobile |
|-------|---------|--------|--------|
| Display 1 | 80px / 96px LH / 40px PS | 64px / 80px LH / 32px PS | 48px / 60px LH / 24px PS |
| Display 2 | 72px / 88px LH / 36px PS | 56px / 72px LH / 28px PS | 44px / 56px LH / 22px PS |
| Display 3 | 64px / 80px LH / 32px PS | 48px / 64px LH / 24px PS | 40px / 52px LH / 20px PS |
| Display 4 | 56px / 72px LH / 28px PS | 44px / 58px LH / 22px PS | 36px / 48px LH / 18px PS |
| Display 5 | 48px / 64px LH / 24px PS | 40px / 52px LH / 20px PS | 32px / 44px LH / 16px PS |
| Display 6 | 40px / 56px LH / 20px PS | 36px / 48px LH / 18px PS | 28px / 40px LH / 14px PS |
| Display 7 | 36px / 48px LH / 18px PS | 32px / 44px LH / 16px PS | 24px / 36px LH / 12px PS |

*LH = Line Height, PS = Paragraph Spacing*

## Heading Styles

Bold weight. Used for section headings and content structure.

| Style | Desktop | Tablet | Mobile |
|-------|---------|--------|--------|
| h1 | 48px / 60px LH / 24px PS | 40px / 52px LH / 20px PS | 32px / 44px LH / 16px PS |
| h2 | 40px / 52px LH / 20px PS | 34px / 46px LH / 17px PS | 28px / 40px LH / 14px PS |
| h3 | 32px / 44px LH / 16px PS | 28px / 40px LH / 14px PS | 24px / 36px LH / 12px PS |
| h4 | 28px / 40px LH / 14px PS | 24px / 36px LH / 12px PS | 20px / 32px LH / 10px PS |
| h5 | 24px / 36px LH / 12px PS | 20px / 32px LH / 10px PS | 18px / 28px LH / 9px PS |
| h6 | 20px / 32px LH / 10px PS | 18px / 28px LH / 9px PS | 16px / 24px LH / 8px PS |

## Body Styles

3 sizes (lg, md, sm) x 3 weights (Regular, Medium, Semibold). Used for paragraphs, descriptions, form text.

### Desktop

| Style | Font Size | Line Height | Paragraph Spacing | Weight |
|-------|-----------|-------------|-------------------|--------|
| body-lg-regular | 18px | 28px | 16px | Regular |
| body-lg-medium | 18px | 28px | 16px | Medium |
| body-lg-semibold | 18px | 28px | 16px | Semibold |
| body-md-regular | 16px | 24px | 14px | Regular |
| body-md-medium | 16px | 24px | 14px | Medium |
| body-md-semibold | 16px | 24px | 14px | Semibold |
| body-sm-regular | 14px | 20px | 12px | Regular |
| body-sm-medium | 14px | 20px | 12px | Medium |
| body-sm-semibold | 14px | 20px | 12px | Semibold |

### Tablet

| Style | Font Size | Line Height | Paragraph Spacing |
|-------|-----------|-------------|-------------------|
| body-lg-* | 17px | 26px | 14px |
| body-md-* | 15px | 22px | 12px |
| body-sm-* | 13px | 18px | 10px |

### Mobile

| Style | Font Size | Line Height | Paragraph Spacing |
|-------|-----------|-------------|-------------------|
| body-lg-* | 16px | 24px | 12px |
| body-md-* | 14px | 20px | 10px |
| body-sm-* | 12px | 18px | 8px |

## Caption Styles

Used for labels, helper text, metadata, timestamps.

### Desktop

| Style | Font Size | Line Height | Paragraph Spacing | Weight |
|-------|-----------|-------------|-------------------|--------|
| caption-lg | 14px | 20px | 10px | Regular |
| caption-md | 12px | 18px | 8px | Regular |
| caption-sm | 11px | 16px | 6px | Regular |
| caption-sm-medium | 11px | 16px | 6px | Medium |
| caption-sm-semibold | 11px | 16px | 6px | Semibold |

### Tablet

| Style | Font Size | Line Height | Paragraph Spacing |
|-------|-----------|-------------|-------------------|
| caption-lg | 13px | 18px | 8px |
| caption-md | 11px | 16px | 6px |
| caption-sm | 10px | 14px | 5px |
| caption-sm-medium | 10px | 14px | 5px |
| caption-sm-semibold | 10px | 14px | 5px |

### Mobile

| Style | Font Size | Line Height | Paragraph Spacing |
|-------|-----------|-------------|-------------------|
| caption-lg | 12px | 16px | 6px |
| caption-md | 10px | 14px | 5px |
| caption-sm | 9px | 12px | 4px |
| caption-sm-medium | 9px | 12px | 4px |
| caption-sm-semibold | 9px | 12px | 4px |

## CSS Variable Naming

```css
:root {
  /* Display */
  --font-display-1-size: 80px;
  --font-display-1-line-height: 96px;
  --font-display-1-spacing: 40px;

  /* Headings */
  --font-h1-size: 48px;
  --font-h1-line-height: 60px;
  --font-h1-spacing: 24px;

  /* Body */
  --font-body-lg-regular-size: 18px;
  --font-body-lg-regular-line-height: 28px;
  --font-body-lg-regular-spacing: 16px;

  /* Caption */
  --font-caption-lg-size: 14px;
  --font-caption-lg-line-height: 20px;
  --font-caption-lg-spacing: 10px;
}

/* Tablet overrides */
@media (max-width: 1023px) {
  :root {
    --font-display-1-size: 64px;
    --font-h1-size: 40px;
    --font-body-lg-regular-size: 17px;
  }
}

/* Mobile overrides */
@media (max-width: 767px) {
  :root {
    --font-display-1-size: 48px;
    --font-h1-size: 32px;
    --font-body-lg-regular-size: 16px;
  }
}
```

## Usage Guidelines

1. **Use semantic heading levels** (h1-h6) for document structure, not visual sizing
2. **Body-md-regular** is the default body text style
3. **Body-sm** is for secondary/supporting text
4. **Caption** styles are for metadata, labels, and helper text
5. **Display** styles are reserved for hero sections and marketing pages
6. **Always use the responsive scale** - it automatically adjusts across breakpoints
7. **Weight variations** (Regular/Medium/Semibold) are for emphasis within the same size
