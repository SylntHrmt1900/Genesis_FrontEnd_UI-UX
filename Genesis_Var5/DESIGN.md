# Design System Strategy: The Ethereal Professional

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Ethereal Professional."** 

We are moving away from the rigid, boxed-in layouts of traditional enterprise software. Instead, we are treating the interface as a high-end digital lens—a series of deep, translucent layers that prioritize focus, depth, and prestige. By leveraging the principles of macOS-inspired glassmorphism, we create an environment that feels expansive rather than restrictive. 

This system breaks the "template" look through **intentional asymmetry** and **tonal depth**. We use generous white space (negative space) and overlapping translucent containers to suggest a physical stack of premium materials. The goal is to make the user feel like they are navigating a high-end physical workspace, where every interaction has weight and every surface has a soul.

---

## 2. Colors & Surface Logic
The palette is rooted in a sophisticated deep-space aesthetic, utilizing `#060e20` (background) as our canvas.

*   **The "No-Line" Rule:** Except for specific "Ghost Borders" (see Elevation), designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be established through background color shifts. For instance, a `surface_container_low` section sitting on a `surface` background creates a natural edge through contrast rather than a hard stroke.
*   **Surface Hierarchy & Nesting:** Treat the UI as a physical stack. 
    *   **Base:** `surface` (#060e20).
    *   **Level 1:** `surface_container_low` (#091328) for secondary navigation or background grouping.
    *   **Level 2:** `surface_container` (#0f1930) for primary content cards.
    *   **Level 3:** `surface_container_highest` (#192540) for active states or floating popovers.
*   **The "Glass & Gradient" Rule:** Floating elements (Modals, Hover Cards, Navigation Bars) must use Glassmorphism. This is achieved by combining a semi-transparent `surface_container_high` (approx 60-80% opacity) with a `backdrop-filter: blur(24px)`. 
*   **Signature Textures:** To add "visual soul," use subtle linear gradients for primary actions. A transition from `primary` (#a3a6ff) to `primary_container` (#9396ff) at a 135-degree angle provides a shimmering, metallic depth that flat colors lack.

---

## 3. Typography: The Editorial Voice
We utilize **Manrope** as our sole typeface. Its geometric yet humanist qualities provide the "Modern Professional" tone required.

*   **The Scale of Authority:** Use a high-contrast scale. `display_lg` (3.5rem) should be used sparingly for hero statements, creating an editorial feel. 
*   **Contextual Weight:** 
    *   **Headlines:** Use `headline_lg` to `headline_sm` in Medium (500) or Semi-Bold (600) weights to anchor the page.
    *   **Body:** `body_lg` (1rem) is our workhorse. Ensure line-height is set to 1.6 for maximum readability against dark, translucent backgrounds.
    *   **Labels:** `label_md` (0.75rem) should use `on_surface_variant` (#a3aac4) to reduce visual noise for auxiliary information.
*   **Hierarchy via Color:** Never use pure white for body text. Use `on_surface` (#dee5ff) for high-priority text and `on_surface_variant` (#a3aac4) for secondary metadata.

---

## 4. Elevation & Depth
In this system, depth is a functional tool, not just a decoration.

*   **The Layering Principle:** Use the **Roundedness Scale** to reinforce nesting. A Level 1 container (e.g., a page section) uses `md` (1.5rem / 24px), while a Level 2 container nested inside it (e.g., a card) uses `DEFAULT` (1rem / 16px).
*   **Ambient Shadows:** For floating glass elements, use an extra-diffused shadow. 
    *   *Formula:* `0px 12px 32px rgba(0, 0, 0, 0.4)`. 
    *   Shadows should never be "gray"; they should be a darkened tint of the background to maintain the deep indigo atmosphere.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a 1px stroke using the `outline_variant` (#40485d) at **20% opacity**. It should feel like a catch-light on the edge of a glass pane, not a structural cage.
*   **Indigo Glows:** Use "Orbital Glows"—large, low-opacity radial gradients of `secondary` (#ac8aff) or `primary` (#a3a6ff) in the background (placed behind glass layers) to simulate light refraction and provide energy to the layout.

---

## 5. Components

### Buttons
*   **Primary:** A gradient of `primary` to `primary_container`. High border-radius (`full`). No border.
*   **Secondary/Glass:** `surface_container_high` with 40% opacity and 12px backdrop-blur. 1px Ghost Border.
*   **Tertiary:** No background. `primary` text. `full` radius on hover with `surface_container_low`.

### Cards & Lists
*   **Cards:** Use `surface_container` with a `DEFAULT` (1rem) radius. **Prohibit divider lines.** 
*   **Separation:** Use `spacing.8` (2.75rem) or `spacing.6` (2rem) of vertical white space to separate list items. If separation is visually difficult, use a subtle background shift to `surface_container_high` on hover.

### Input Fields
*   **Styling:** Background of `surface_container_lowest` (#000000). 1px Ghost Border using `outline`.
*   **State:** On focus, the border transitions to 1px `primary` with a subtle 4px `primary_dim` outer glow.

### Chips
*   **Action Chips:** `surface_container_high` with a `sm` (0.5rem) radius. Text in `on_surface`.
*   **Selection Chips:** When active, use `secondary_container` (#5516be) with `on_secondary_container` (#d9c8ff) text.

---

## 6. Do's and Don'ts

### Do:
*   **Do** allow background "glows" to bleed through glass containers to create a sense of place.
*   **Do** use asymmetrical layouts (e.g., a wider left column and a slim, floating glass right column) to feel more custom and less like a dashboard template.
*   **Do** use the `xl` (3rem) spacing for major section breathing room.

### Don't:
*   **Don't** use pure black (#000000) for anything other than the most recessed input fields or the absolute lowest background layer.
*   **Don't** use 100% opaque borders. It breaks the "Ethereal Professional" illusion and makes the UI feel heavy and dated.
*   **Don't** crowd the glass. Glassmorphism requires negative space to work; if the interface is too busy, the blur effect becomes visual noise rather than a premium detail.
*   **Don't** use standard "drop shadows" on flat surfaces. Only floating glass elements deserve a shadow.