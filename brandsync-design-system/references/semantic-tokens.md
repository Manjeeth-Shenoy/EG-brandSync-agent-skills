# BrandSync Semantic Token Reference

Semantic tokens map primitive color shades to UI interaction states. They support light and dark mode, and are the recommended way to apply colors in components.

## Token Naming Convention

```
--color-{category}-{state}
```

Where:
- **category**: primary, neutrals, success, error, warning, information
- **state**: default, hover, focused, pressed, container, container-hover, container-focused, container-pressed

## Primary Tokens

The primary color changes based on the selected brand color (purple, cobalt, blue, etc.).

### Light Mode
| Token | Shade | Description |
|-------|-------|-------------|
| `--color-primary-default` | 600 | Base interactive state - buttons, links, active elements |
| `--color-primary-hover` | 700 | Hover state for primary elements |
| `--color-primary-focused` | 700 | Focus state (keyboard navigation) |
| `--color-primary-pressed` | 800 | Active/pressed state |
| `--color-primary-container` | 50 | Background surfaces, cards with primary tint |
| `--color-primary-container-hover` | 100 | Hover state for primary containers |

### Dark Mode
| Token | Shade | Description |
|-------|-------|-------------|
| `--color-primary-default` | 400 | Base interactive state |
| `--color-primary-hover` | 300 | Hover state |
| `--color-primary-focused` | 300 | Focus state |
| `--color-primary-pressed` | 200 | Active/pressed state |
| `--color-primary-container` | 950 | Background surfaces |
| `--color-primary-container-hover` | 900 | Container hover state |

## Neutral Tokens

Used for text, borders, backgrounds, and structural UI elements.

### Light Mode
| Token | Shade | Description |
|-------|-------|-------------|
| `--color-neutrals-default` | 700 | Primary text, icons |
| `--color-neutrals-hover` | 800 | Hover state for neutral elements |
| `--color-neutrals-focused` | 800 | Focus state |
| `--color-neutrals-pressed` | 900 | Active/pressed state |
| `--color-neutrals-container` | 25 | Page background, base surface |
| `--color-neutrals-container-hover` | 50 | Surface hover state |
| `--color-neutrals-container-focused` | 100 | Surface focus state |
| `--color-neutrals-container-pressed` | 200 | Surface pressed state |

### Dark Mode
| Token | Shade | Description |
|-------|-------|-------------|
| `--color-neutrals-default` | 300 | Primary text, icons |
| `--color-neutrals-hover` | 200 | Hover state |
| `--color-neutrals-focused` | 200 | Focus state |
| `--color-neutrals-pressed` | 50 | Active/pressed state |
| `--color-neutrals-container` | 900 | Page background |
| `--color-neutrals-container-hover` | 800 | Surface hover state |
| `--color-neutrals-container-focused` | 800 | Surface focus state |
| `--color-neutrals-container-pressed` | 700 | Surface pressed state |

## Success Tokens

Positive actions, confirmations, completed states.

### Light Mode
| Token | Shade |
|-------|-------|
| `--color-success-default` | 600 |
| `--color-success-hover` | 700 |
| `--color-success-focused` | 700 |
| `--color-success-pressed` | 800 |
| `--color-success-container` | 100 |

### Dark Mode
| Token | Shade |
|-------|-------|
| `--color-success-default` | 400 |
| `--color-success-hover` | 300 |
| `--color-success-focused` | 300 |
| `--color-success-pressed` | 200 |
| `--color-success-container` | 800 |

## Error Tokens

Destructive actions, validation errors, critical alerts.

### Light Mode
| Token | Shade |
|-------|-------|
| `--color-error-default` | 600 |
| `--color-error-hover` | 700 |
| `--color-error-focused` | 700 |
| `--color-error-pressed` | 800 |
| `--color-error-container` | 100 |

### Dark Mode
| Token | Shade |
|-------|-------|
| `--color-error-default` | 400 |
| `--color-error-hover` | 300 |
| `--color-error-focused` | 300 |
| `--color-error-pressed` | 200 |
| `--color-error-container` | 950 |

## Warning Tokens

Caution states, non-critical alerts.

### Light Mode
| Token | Shade |
|-------|-------|
| `--color-warning-default` | 600 |
| `--color-warning-hover` | 700 |
| `--color-warning-focused` | 700 |
| `--color-warning-pressed` | 800 |
| `--color-warning-container` | 200 |

### Dark Mode
| Token | Shade |
|-------|-------|
| `--color-warning-default` | 400 |
| `--color-warning-hover` | 300 |
| `--color-warning-focused` | 300 |
| `--color-warning-pressed` | 200 |
| `--color-warning-container` | 800 |

## Information Tokens

Informational messages, tooltips, contextual guidance.

### Light Mode
| Token | Shade |
|-------|-------|
| `--color-information-default` | 500 |
| `--color-information-hover` | 700 |
| `--color-information-focused` | 700 |
| `--color-information-pressed` | 800 |
| `--color-information-container` | 100 |

### Dark Mode
| Token | Shade |
|-------|-------|
| `--color-information-default` | 400 |
| `--color-information-hover` | 300 |
| `--color-information-focused` | 300 |
| `--color-information-pressed` | 200 |
| `--color-information-container` | 800 |

## Usage Examples

### CSS Custom Properties
```css
:root {
  /* Primary - using purple as the brand color */
  --color-primary-default: var(--primary-600);     /* #5E47E6 */
  --color-primary-hover: var(--primary-700);        /* #4B35C9 */
  --color-primary-container: var(--primary-50);     /* #F3EFFB */

  /* Neutrals */
  --color-neutrals-default: var(--neutral-700);     /* #4D535F */
  --color-neutrals-container: var(--neutral-25);    /* #F9FAFB */
}

.dark {
  --color-primary-default: var(--primary-400);      /* #8676FE */
  --color-primary-hover: var(--primary-300);         /* #A49AFF */
  --color-primary-container: var(--primary-950);     /* #201463 */

  --color-neutrals-default: var(--neutral-300);      /* #A0A5B4 */
  --color-neutrals-container: var(--neutral-900);    /* #21262E */
}
```

### Component Pattern
```css
/* Button using semantic tokens */
.btn-primary {
  background-color: var(--color-primary-default);
  color: white;
}
.btn-primary:hover {
  background-color: var(--color-primary-hover);
}
.btn-primary:focus-visible {
  background-color: var(--color-primary-focused);
  outline: 2px solid var(--color-primary-default);
  outline-offset: 2px;
}
.btn-primary:active {
  background-color: var(--color-primary-pressed);
}

/* Alert using semantic tokens */
.alert-error {
  background-color: var(--color-error-container);
  color: var(--color-error-default);
  border: 1px solid var(--color-error-default);
}

/* Card using neutral tokens */
.card {
  background-color: var(--color-neutrals-container);
  color: var(--color-neutrals-default);
}
.card:hover {
  background-color: var(--color-neutrals-container-hover);
}
```

## Token Category Descriptions

| Category | Purpose |
|----------|---------|
| **Primary** | Main brand color for the most important actions - primary buttons, active states, links, focus rings |
| **Neutrals** | Structure and content - text, backgrounds, borders, dividers, disabled states |
| **Success** | Positive feedback - completed actions, valid inputs, confirmation messages |
| **Error** | Problems requiring attention - invalid inputs, failed actions, destructive buttons |
| **Warning** | Caution - non-critical alerts, approaching limits, pending actions |
| **Information** | Contextual help - tooltips, informational banners, general notices |
