# Design System Strategy: The Schematic Methodology

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Schematic"**

This design system is engineered to move away from the "soft and social" corporate aesthetic and toward the precision of high-performance technical tools. We are building a professional environment for electronics engineers that mirrors the density of a complex PCB (Printed Circuit Board) layout while maintaining the editorial clarity of a high-end technical journal.

By leveraging **intentional asymmetry**, we break the predictable "boxed" web layout. Content should feel like it is part of a larger, interconnected system. We utilize high-contrast typography scales and overlapping hexagonal motifs to create a sense of mechanical depth. This isn't just a community platform; it’s a workstation.

---

## 2. Colors
Our palette is rooted in a deep, atmospheric dark mode foundation, punctuated by high-luminance technical accents that mimic LEDs and active traces.

### The Palette
- **Background (`#121318`):** The non-reflective base of our "workstation."
- **Primary / Circuit Board Green (`#00FF41`):** Use for active states and critical paths.
- **Secondary / Resistor Orange (`#FE6B00`):** Use for alerts, warnings, or secondary CTA differentiation.
- **Solder Silver / Tertiary (`#F9F9F8`):** Use for high-readability labels and technical metadata.

### The "No-Line" Rule
Standard 1px solid borders are strictly prohibited for sectioning. Structural definition must be achieved through:
1. **Background Shifting:** Use `surface-container-low` for secondary sidebars against the `background` main stage.
2. **Glow Traces:** Replace standard borders with a 1px "Ghost Border" using `outline-variant` at 20% opacity, or a subtle outer glow for cards.

### Surface Hierarchy & Nesting
Think of the UI as physical layers of a substrate. 
- **Main Stage:** `surface`
- **Primary Content Blocks:** `surface-container`
- **Nested Data (e.g., code snippets inside a post):** `surface-container-highest`

### The "Glass & Gradient" Rule
To add soul to the technical rigidity, use **Glassmorphism** for floating headers or navigation rails. Apply a backdrop blur (20px+) to `surface-container` colors with 80% opacity. For CTAs, use a linear gradient from `primary` to `primary-container` to simulate the glow of an illuminated component.

---

## 3. Typography
The type system balances geometric "Brutalist" headlines with high-density "Technical" body text.

- **Display & Headlines (Space Grotesk):** This is our "mechanical" font. Its wide stance and geometric apertures feel engineered. Use `display-lg` (3.5rem) for hero moments and `headline-md` (1.75rem) for thread titles.
- **Body & Labels (Inter / Technical UI):** Chosen for its exceptional legibility at high information densities. 
    - Use `body-md` (0.875rem) for main forum text to maximize information density.
    - Use `label-sm` (0.6875rem) for technical metadata (e.g., voltage specs, timestamps, user IDs).

---

## 4. Elevation & Depth
Depth is not communicated via shadows alone, but through **Tonal Layering**.

- **The Layering Principle:** A "card" is defined by being a step lighter than the surface it sits on. Place a `surface-container-low` post on a `background` feed.
- **Ambient Shadows:** For floating modals, use a 32px blur with 6% opacity. The shadow color must be a tinted version of `surface-tint` (`#00E639`) to mimic the green bounce-light from a circuit board.
- **Hexagonal Masking:** Use the hexagonal honeycomb pattern as a subtle `background` overlay at 3% opacity. It should feel like a watermark on a blueprint.
- **Ghost Borders:** When high-density data requires clear separation, use `outline-variant` at 15% opacity. It should look like a laser-etched guide, not a heavy stroke.

---

## 5. Components

### Buttons
- **Shape:** `0px` radius (Sharp corners) to maintain an edgy, pro-tool feel.
- **Primary:** `primary-container` background with `on-primary-container` text. High-visibility "Power On" state.
- **Secondary:** Transparent background with a `primary` ghost border (20% opacity) and a sharp hover transition to 100% opacity.

### Cards & Lists
- **No Dividers:** Forbid the use of horizontal lines. Use `8px` (Spacing 2) of vertical white space or a shift from `surface-container` to `surface-container-high` to denote a new item.
- **Glowing Borders:** Critical or "Featured" cards use a 1px `primary` border with a 4px `primary` outer glow (8% opacity).

### Inputs & Fields
- **Technical Inputs:** Rectangular (`0px` radius). Use `surface-container-highest` for the field background. The active state is a 1px `primary` bottom-border only, mimicking a terminal prompt.

### The "Honey-Chip" (Unique Component)
- **Chips:** For categorization (e.g., "Arduino," "FPGA"), use a hexagonal clipped shape or a sharp-edged box with the `secondary-fixed-dim` (`#FFB693`) for the label to differentiate it from UI actions.

---

## 6. Do's and Don'ts

### Do
*   **Do** maximize information density. Engineers prefer seeing more data at once than having large, wasted margins.
*   **Do** use `Solder Silver` (`tertiary`) for secondary text to keep the hierarchy distinct from the `primary` green.
*   **Do** align elements to a strict technical grid, but allow specific "circuit traces" (decorative lines) to break the grid diagonally.

### Don't
*   **Don't** use rounded corners. A `0px` radius is our signature. Anything above `2px` feels "corporate-round" and must be avoided.
*   **Don't** use standard blue for links. Links are always `primary` (`#00FF41`).
*   **Don't** use drop-shadows on cards. Rely on background color shifts and ghost borders.
*   **Don't** use "Light Mode." This system is engineered for low-light lab environments; there is no light-mode equivalent.

---

## 7. Spacing Scale
Precision is paramount. We use a tight scale to enable information density.
- **Micro-spacing:** `0.2rem` (Token 1) for label/icon pairing.
- **Standard Padding:** `0.9rem` (Token 4) for card internals.
- **Section Gaps:** `2.25rem` (Token 10) to provide air between dense data modules.