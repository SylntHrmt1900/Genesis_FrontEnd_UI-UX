# Design System Strategy: Luxe Digital Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Obsidian Luminary."** 

This system moves away from the flat, sterile grids of traditional social platforms to create a high-end, immersive environment. By blending the deep, infinite depth of obsidian surfaces with the vibrant energy of cosmic mesh gradients, we transition from a "utility app" to a "curated digital experience." The aesthetic is intentional, using asymmetry and glassmorphism to suggest a physical workspace of stacked frosted glass and light.

Key pillars include:
*   **Depth through Translucency:** Moving beyond shadows to use `backdrop-blur` and varying opacity.
*   **Organic Movement:** Using mesh gradients (`primary` to `tertiary`) to guide the eye toward focal points.
*   **Editorial Authority:** High-contrast typography scales that prioritize legibility and status.

---

## 2. Colors & Surface Philosophy

### The Obsidian Canvas
The foundation is built on `#060e20` (`background`). This is not a flat black, but a deep, atmospheric navy. All color application must respect this depth.

*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for structural sectioning. To define a content area (like a feed card or sidebar), use a background shift from `surface` to `surface-container-low` or `surface-container-high`. 
*   **The Glass & Gradient Rule:** For high-impact elements like the "Post" composer or "Trending" cards, use a `surface-variant` color at 40% opacity with a `24px` backdrop blur. Enhance this by placing a subtle mesh gradient transition from `primary` (#a3a6ff) to `tertiary` (#c180ff) in the background layer behind the glass.
*   **Solar Accents:** Use `secondary` (#ff7441) exclusively for high-conversion CTAs. This "Solar Orange" should be treated as a spark of light against the obsidian background—high impact, used sparingly.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack. 
1.  **Level 0 (Base):** `surface` (#060e20).
2.  **Level 1 (Sectioning):** `surface-container-low`.
3.  **Level 2 (Cards/Content):** `surface-container` or Glassmorphic containers.
4.  **Level 3 (Floating/Active):** `surface-bright` with ambient glow.

---

## 3. Typography: The Manrope Scale
We use **Manrope** for its balance of geometric precision and human warmth. 

*   **Display (Editorial Impact):** Use `display-lg` (3.5rem) with -2% letter spacing for hero headers. This creates a bold, editorial feel that demands attention.
*   **Headlines (Navigation/Clarity):** `headline-md` (1.75rem) should be used for section headers. Ensure a generous `16` (5.5rem) spacing scale above headers to create "breathing room."
*   **Body (Utility):** `body-lg` (1rem) is the workhorse. Use `on-surface-variant` (#a3aac4) for secondary metadata to maintain a soft visual hierarchy.
*   **Signature Styling:** All titles (`title-lg`) should have a subtle text-shadow of 0 2px 4px rgba(0,0,0,0.3) to ensure they pop against mesh-gradient backgrounds.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are replaced by **Ambient Light** and **Tonal Stacking**.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-highest` card inside a `surface-container-low` area. The 10% brightness difference creates a natural, sophisticated lift.
*   **Ambient Shadows:** For floating modals or dropdowns, use a multi-layered shadow: 
    *   `0px 4px 20px rgba(0, 0, 0, 0.4)` 
    *   `0px 10px 40px rgba(163, 166, 255, 0.08)` (A subtle tint of `primary` to mimic light bleed).
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` at 15% opacity. This "Ghost Border" provides a container without breaking the "Luxe" flow.
*   **Subtle Glows:** Active states (like a focused input) should use a 1px border of `primary_dim` with a `box-shadow: 0 0 12px rgba(163, 166, 255, 0.3)`.

---

## 5. Components

### Buttons
*   **Primary (Solar):** Background: `secondary` (#ff7441), Text: `on_secondary`. Use `xl` (1.5rem) roundedness for a pill-shaped, premium feel.
*   **Secondary (Glass):** Backdrop-blur (12px), Background: `surface-variant` at 20% opacity, 1px Ghost Border.
*   **Tertiary:** Ghost button with `primary` text and a subtle underline on hover.

### Input Fields
*   **State:** Dark Obsidian. Use `surface_container_lowest` for the field background.
*   **Interaction:** On focus, the background transitions to `surface_container_high` with a `primary` glow. No harsh 1px black borders.

### Cards & Feed Items
*   **Construction:** Forbid dividers. Use `Spacing 4` (1.4rem) between items. 
*   **Status:** Use a vertical gradient strip (primary to tertiary) on the far-left edge of "Featured" posts to denote status without cluttering the UI.

### Glassmorphic Chips
*   Used for tags and categories. Use `primary_container` at 30% opacity with `label-md` text. The roundedness should be `full` (9999px).

---

## 6. Do's and Don'ts

### Do
*   **Do** use intentional asymmetry. A profile card can be slightly offset or overlap a background gradient to feel "bespoke."
*   **Do** use `20` and `24` spacing scales to create massive margins. Premium products are defined by the space they *don't* fill.
*   **Do** use "Solar Orange" (`secondary`) for exactly one thing per screen: the most important action.

### Don't
*   **Don't** use `#000000` for backgrounds. It kills the depth. Always use the `surface` token.
*   **Don't** use 100% opaque borders. They are the "budget" version of UI design.
*   **Don't** use standard "drop shadows." If it looks like a 2010 Photoshop effect, it’s too heavy. Keep them diffused and tinted.
*   **Don't** crowd the interface. If the "community" feel starts looking like a cluttered forum, increase your white space by two increments on the scale.