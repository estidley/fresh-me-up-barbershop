---
name: Fresh Me Up Barbershop
description: A monochrome shop identity built from condensed type and outlined hexagons.
colors:
  ink: "#0b0b0b"
  paper: "#f8f8f8"
  gray: "#dadada"
  muted: "#b8b8b8"
  dark-hover: "#333"
  emblem-hover: "#777"
  rule: "#aaa"
  disclosure-rule: "#666"
  menu-border: "#888"
  nav-rule: "#555"
typography:
  display:
    fontFamily: "Anton, sans-serif"
    fontSize: "clamp(110px, 15.24vw, 274px)"
    fontWeight: 400
    lineHeight: 0.87
    letterSpacing: "-0.025em"
  headline:
    fontFamily: "Anton, sans-serif"
    fontSize: "clamp(54px, 6.7vw, 104px)"
    fontWeight: 400
    lineHeight: 1.1
    letterSpacing: "-0.025em"
  title:
    fontFamily: "Barlow Condensed, sans-serif"
    fontSize: "26px"
    fontWeight: 600
    letterSpacing: "0.025em"
  body:
    fontFamily: "Manrope, sans-serif"
    lineHeight: 1.55
  label:
    fontFamily: "Barlow Condensed, sans-serif"
    fontSize: "22px"
    fontWeight: 600
    letterSpacing: "0.085em"
spacing:
  gutter: "clamp(20px, 3.9vw, 72px)"
  small: "12px"
  medium: "24px"
  column: "32px"
components:
  button-light:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.ink}"
    typography: "{typography.label}"
    padding: "12px 28px"
  button-light-hover:
    backgroundColor: "{colors.gray}"
  button-dark:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
    typography: "{typography.label}"
    padding: "12px 28px"
  button-dark-hover:
    backgroundColor: "{colors.dark-hover}"
  service-row:
    textColor: "{colors.paper}"
    typography: "{typography.title}"
    padding: "12px 0"
---

# Design System: Fresh Me Up Barbershop

## Overview

**Creative North Star: "The Hex Shop Sign"**

Heavy condensed type gives the shop name its scale. Black and off-white fields, a gray address strip, and outlined hexagons carry the identity without color accents. The white space around the main hexagon is part of its shape.

Service names and prices sit in open rows. Square booking controls and plain supporting copy keep the page direct. This records the implemented world selected in mockup A; the page-specific composition remains in `.impeccable/surfaces/index-html.md`.

**Key Characteristics:**

- Oversized condensed display type with plain supporting copy.
- Black, off-white, and neutral gray only.
- Outlined hexagons repeated at distinct scales.
- Open service rows and square booking controls.

## Colors

The palette is entirely neutral; contrast and field size supply emphasis.

### Neutral

- **Ink:** display lettering, controls on light surfaces, header, services, and footer.
- **Paper:** hero and visit grounds, plus text and controls on black.
- **Gray:** the address strip and light-button hover state.
- **Muted:** supporting copy on black and service-row hover text.
- **Dark hover:** the lighter state of a black booking control.
- **Emblem hover:** the hero hexagon's outline while the booking control is hovered.
- **Rule:** service separators and the desktop visit divider.
- **Disclosure rule, menu border, and nav rule:** distinct gray strokes for those controls.

**The Monochrome Rule.** Use black, off-white, and gray; do not introduce a colored accent.

## Typography

Anton, with a sans-serif fallback, carries display and section headings. Barlow Condensed, with a sans-serif fallback, carries navigation, buttons, prices, service names, and the hexagon lettering. Manrope, with a sans-serif fallback, carries prose and contact details. Fonts are self-hosted with `font-display: swap`: Anton regular, Barlow Condensed semibold, and Manrope regular, medium, and semibold.

The frontmatter records the core roles. The two-line uppercase shop name has different horizontal scaling on its first and second lines (1.28 and 1.12); this belongs to the identity treatment, not ordinary headings. The service heading has its own fluid scale (`clamp(42px, 6.6vw, 106px)`). Supporting service copy is 18px and limited to 29ch on desktop. There is no modular type scale.

Use uppercase for navigation, booking labels, and the hexagon identity. Service names and prose use sentence case. Keep the condensed display face out of longer paragraphs.

## Layout

The centered shell stops at 1800px and uses the fluid gutter in the frontmatter. The desktop hero has 1.4:1 columns and an 8% gap. Service and visit sections share a 1.45:1 grid and a 5.5% gap. Broad fields divide the page: light hero, gray strip, black services, light visit, and black footer.

At 1000px and below, the hero becomes 1.3:1 with a 4% gap; services and visit become 1.15:1 with a 32px gap. The service heading can wrap. At 650px and below, the header is 76px tall, desktop navigation gives way to a Menu control, and all content grids become one column. The mobile hero uses a 24px gap. Its booking control is full-width with a 52px minimum height; the hexagon remains visible below it, centered at `min(240px, 100%)` wide.

The mobile shop name uses `clamp(98px, 31.5vw, 180px)` with leading of 0.94. The hexagon's inner inset becomes 4px. The address strip and footer stack, the visit divider disappears, and service rows use 24px type with a 62px minimum height. Service supporting copy grows to a 36ch measure. Keep the hexagon in the mobile flow rather than removing it.

## Elevation & Depth

There are no shadows or gradients. Large areas of reversed contrast establish sections, while neutral rules organize the service menu. Hexagons use an outer shape and inset background shape to create flat outlines.

## Shapes

Booking controls have square corners. The recurring hexagon uses points at top and bottom with vertical sides, expressed as a six-point CSS polygon. The large hero emblem, small header mark, and row markers share that geometry. Arrow icons use inline SVG with square line caps and miter joins; disclosures use an inline SVG plus.

## Components

**Booking controls.** The base control has a 54px minimum height, a thin border, and uppercase condensed labels. Dark and light variants invert their surrounding field. The desktop hero control has a 64px minimum height and 338px minimum width. Hover changes its background; transitions take 0.2s with ease timing. Hovering the hero booking control also changes the nearby hexagon outline to gray through `:has()`.

**Service rows.** An entire row links to Booksy. A three-column grid holds service name, price, and a decorative outlined hexagon. A thin gray rule separates rows; hover changes the text and marker color to muted gray. The desktop row has a 59px minimum height.

**More services.** A native `details`/`summary` disclosure holds extras. Its inline SVG plus rotates 45 degrees when open. The summary has a 44px minimum height and 18px body type. Definition-list rows align service names and prices; tabular numerals keep the expanded prices steady.

**Navigation.** The mobile Menu button toggles `aria-expanded` and the hidden navigation, changes its label to Close, closes after a link selection, and closes on Escape while returning focus. Resizing to desktop closes the menu.

**Hexagon identity.** The desktop hero emblem has a 444px maximum width and a 444:504 aspect ratio. The header mark and service markers echo the same outline. These shapes are decorative; the shop name, address, and booking action remain readable HTML.

All links, buttons, and summaries have a current-color focus outline (3px, offset 6px). Reduced-motion preference disables transitions and smooth scrolling. There are no forms, generic cards, or chips in the current implementation.

## Do's and Don'ts

### Do:

- **Do** keep condensed display type, outlined hexagons, and monochrome fields distinct from Pasha's gold and serif world.
- **Do** retain the centered mobile hexagon below the full-width booking control.
- **Do** keep service rows open and booking, contact details, and disclosures as accessible HTML.

### Don't:

- **Don't** add colored accents, invented shop photographs, or invented reviews.
- **Don't** replace the square controls and open rows with rounded cards or shadowed panels.
- **Don't** apply the shop name's horizontal scaling to ordinary headings or body copy.
