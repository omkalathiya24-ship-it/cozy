# COZY Typography Style Guide

This document outlines the comprehensive typography system implemented for the COZY luxury apparel platform. The system utilizes a curated selection of 10 serif fonts to create a clean, minimalist, and high-end aesthetic.

## Font Strategy

We use Google Fonts as a high-performance web font service, utilizing `font-display: swap` and preloading for optimal loading times.

### Font Mapping (10 Specified Fonts)

| Original Concept | Google Font Equivalent | Usage Category | CSS Variable |
| :--- | :--- | :--- | :--- |
| DOWNTOWN | **Forum** | Primary Headings (H1) | `--font-h1` |
| Silver Lake (Restora) | **EB Garamond** | Secondary Headings (H2) | `--font-h2` |
| Bel Air (Ortica) | **Cormorant Garamond** | Sub-headings (H3) | `--font-h3` |
| Glendale (Lovato) | **Libre Baskerville** | UI Sub-titles (H4) | `--font-h4` |
| MELROSE (Messapia) | **Prata** | Component Titles (H5) | `--font-h5` |
| PALISADES (Amagro) | **Bodoni Moda** | Small Titles (H6) | `--font-h6` |
| Burbank (Big Caslon) | **Libre Caslon Display** | Large Display Text | `--font-font-display` |
| Pasadena (Garogier) | **Alice** | Body Text / Paragraphs | `--font-body` |
| HOLLYWOOD | **Cinzel** | Navigation / UI Labels | `--font-nav` |
| MALIBU (Coconat) | **Italiana** | Accent / Luxury Text | `--font-accent` |

## Typography Scale

A responsive scale is used to ensure consistency across all devices.

- **5XL (48px):** `.display-text` (Hero Headings)
- **4XL (36px):** `h1` (Main Page Headings)
- **3XL (30px):** `h2` (Section Headings)
- **2XL (24px):** `h3` (Component Headings)
- **XL (20px):** `h4` (Large UI Text)
- **LG (18px):** `h5` (Standard UI Headings)
- **Base (16px):** `body`, `h6` (Primary Text)
- **SM (14px):** `.nav-link`, `.small` (Secondary Text)
- **XS (12px):** `.extra-small` (Captions/Badges)

## Usage Rules

1. **Headings:** Always use the defined `h1-h6` tags or classes.
2. **Body Text:** Use `p` tags. Default line-height is 1.6 (`--lh-base`) for readability.
3. **Luxury Accents:** Apply the `.luxury-text` class for special accent text (e.g., "Established 2026").
4. **Navigation:** Use the `.nav-link` class which applies the `Cinzel` font with appropriate letter-spacing.

## Accessibility Considerations

- **Contrast:** Ensure all text meets a minimum contrast ratio of 4.5:1 against its background.
- **Readability:** Minimum font size for body text is 16px.
- **Line Height:** Maintain at least 1.5 line-height for long-form content.

## Maintenance

To add a new font or modify an existing one:
1. Update the Google Fonts import in `index.html`.
2. Update the corresponding CSS variable in `:root` within `styles.css`.
3. If preloading is required, add the appropriate `<link rel="preload">` tag in `index.html`.

## Commercial Licensing

All fonts used in this system are sourced from **Google Fonts** and are licensed under the **Open Font License (OFL)**. This allows for free use in commercial projects without additional licensing fees.
