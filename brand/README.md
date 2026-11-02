# Pandion Labs color system

Status: adopted by the founder on 2026-11-02. Applies to Pandion Labs and its products, including Fishhawk. The reference appearance is [pandionlabs.com](https://pandionlabs.com/).

The company site's color theme is the shared product-family palette. Product interfaces, documentation, and marketing should use these values and roles consistently. Layout and information density can adapt to each surface.

## Palette

| CSS token | Value | Role |
| --- | --- | --- |
| `--pandion-paper` | `#f5f3eb` | Warm ivory page background; text on deep green |
| `--pandion-ink` | `#193d35` | Deep forest green body text, navigation, primary buttons, inverse surfaces |
| `--pandion-muted` | `#5e6c62` | Sage secondary text on light surfaces |
| `--pandion-line` | `#cdd1c5` | Quiet dividers and decorative borders |
| `--pandion-rust` | `#af4727` | Restrained rust emphasis, hover treatment, focus indicators on light surfaces |
| `--pandion-surface` | `#e8eadd` | Recessed sage panels and grouped content |
| `--pandion-sand` | `#d5b993` | Warm emphasis on deep green surfaces |

## Implementation

[colors.css](colors.css) is the reusable source. The company site's `styles.css` imports it and maps the existing site aliases to these tokens. Product implementations should vendor a reviewed copy at a recorded commit or consume it through their build, then map the primitives to their framework's semantic theme variables. Avoid a runtime dependency on the company site's hosting.

Use semantic names such as background, foreground, primary, muted, and border in components. Keep raw palette values in the theme layer. When changing a shared value, review and update its consumers together.

Fishhawk adoption covers its Web UI, public docs site, and marketing surfaces. Its existing `docs/BRAND_FOUNDATIONS.md` color direction should cite this reference and replace the statement that exact brand colors are deferred. Product names, typefaces, logos, and layout remain independent design decisions; this decision establishes the color family.

## Usage

- Light surfaces: paper background, ink foreground, muted supporting text, sage panels. Primary actions use ink with paper text; rust draws attention sparingly.
- Inverse surfaces: ink background, paper foreground, sand emphasis. Rust is not body text on ink.
- Product dark mode should retain the forest-green and warm-neutral family with verified text and control contrast. The company site's inverse section is a starting point, not a complete approved dark-mode theme.
- Success, warning, error, and destructive-action colors retain distinct semantic meanings. Pair states with text or icons. Rust emphasis alone does not mean approved, failed, or safe.
- Quiet divider color is decorative. Essential input boundaries, focus indicators, and state indicators need sufficient contrast in their actual adjacent context.
- Typography on the company site is DM Sans with Libre Caslon Display headlines. This palette decision does not require display serifs in dense product interfaces.

## Verified text pairs

Ratios computed from sRGB relative luminance. These pairs exceed 4.5:1 for normal text; opacity, overlays, and other backgrounds require their own check.

| Foreground | Background | Contrast |
| --- | --- | --- |
| Ink | Paper | 10.74:1 |
| Paper | Ink | 10.74:1 |
| Muted | Paper | 4.98:1 |
| Rust | Paper | 5.04:1 |
| Muted | Surface | 4.54:1 |

Before releasing a product adaptation, check light and dark themes, keyboard focus, hover, selected, disabled, and semantic status states, plus representative desktop and mobile screens.
