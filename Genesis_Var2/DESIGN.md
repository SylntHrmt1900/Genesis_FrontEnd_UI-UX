# Design System Strategy: The Luminescent Professional

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Obsidian"**
This design system moves away from the sterile, rigid grids of traditional corporate platforms. It treats the interface not as a flat screen, but as a deep, pressurized space—like light reflecting off polished obsidian. By blending the community-driven density of Reddit with the authoritative poise of LinkedIn, we create an environment that feels both high-stakes and highly collaborative. 

To break the "template" look, we utilize **Intentional Asymmetry**. Larger editorial headlines are offset against dense data modules, and floating "Glassmorphism" layers break the container boundaries to suggest a UI that breathes. We do not "box" content; we "surface" it.

---

## 2. Colors & Tonal Depth
The palette is anchored in a monolithic dark blue (`#080e19`) and punctuated by a "Fusion Orange" (`#ff9159`).

*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Structural separation is achieved exclusively through background shifts. For instance, a Feed Item (`surface-container-low`) sits directly on the Global Feed Background (`surface`), distinguished only by a subtle shift in luminance.
*   **Surface Hierarchy & Nesting:** Use the `surface-container` tiers to create organic depth. 
    *   **Level 0 (Base):** `surface` (#080e19) for the primary application background.
    *   **Level 1 (Sections):** `surface-container-low` (#0d1320) for sidebar groupings or secondary feeds.
    *   **Level 2 (Active Cards):** `surface-container-high` (#18202f) for primary content cards or hover states.
*   **The "Glass & Gradient" Rule:** Floating navigation bars or modal headers must use a semi-transparent `surface-variant` with a `20px` backdrop-blur. 
*   **Signature Textures:** Main CTAs must use a linear gradient: `primary` (#ff9159) to `primary-container` (#ff7a2f) at a 135-degree angle. This adds a "glowing filament" effect that flat HEX codes lack.

---

## 3. Typography: Editorial Authority
We utilize **Manrope** for its geometric yet warm structure, supported by **Inter** for high-density utility.

*   **Display & Headlines (Manrope):** Used for profile names and community titles. Use `display-md` with `tight` letter-spacing (-0.02em) to create a sophisticated, editorial feel.
*   **Body (Manrope):** All professional insights and community posts use `body-lg`. This ensures readability in dark mode, where white text on dark backgrounds can "bloom" if too small.
*   **Labels (Inter):** Functional metadata (timestamps, "Promoted," "Online") uses `label-md`. The switch to Inter signals a shift from "Content" to "Utility."

---

## 4. Elevation & Depth
In this system, "Up" means "Brighter," not "Shadowier."

*   **The Layering Principle:** To lift a card, move it from `surface-container-low` to `surface-container-highest`. No shadow is needed; the eye perceives the lighter tone as being closer to the light source.
*   **Ambient Shadows:** If a component must float (e.g., a Profile Dropdown), use a shadow with a `48px` blur, `0%` spread, and `8%` opacity, tinted with `primary` (#ff9159) to simulate the orange accent light reflecting off the dark surface.
*   **The "Ghost Border" Fallback:** For accessibility in input fields, use `outline-variant` (#424855) at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Use for persistent elements like the "Create Post" floating action bar. Combine `surface-container-highest` at 60% opacity with a `16px` blur to keep the user grounded in the feed context.

---

## 5. Components & Primitive Logic

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary-container`), `xl` (1.5rem) corner radius, and `on-primary` (#531e00) text for high-contrast legibility.
*   **Tertiary (Ghost):** No background. Use `primary` text. On hover, apply a `surface-bright` background at 10% opacity.

### Community Cards
*   **Style:** Forbid dividers. Use `1.5rem` (scale 6) of vertical whitespace to separate the "Author" header from the "Post Content" body. 
*   **Radius:** Always use `xl` (1.5rem/24px) for cards to maintain the "soft modern" aesthetic.

### Pro-Feed Chips
*   **Filter Chips:** Use `surface-container-highest` with `label-md` text. When selected, transition to `secondary-container` with an `on-secondary-container` text color.

### Input Fields
*   **The "Deep Well" Look:** Background should be `surface-container-lowest` (#000000) to create a recessed effect. Use `xl` corner radius. Error states use a `ghost border` of `error` (#ff7351) at 40% opacity.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins (e.g., more padding on the left than the right in headers) to create a premium, custom layout.
*   **Do** use the `primary-dim` tone for hover states on orange elements to create a "cooling" effect.
*   **Do** allow background imagery or profile banners to bleed behind the `surface-container` layers using glassmorphism.

### Don’t:
*   **Don't** use `#000000` (Black) for anything other than `surface-container-lowest` or input wells. Pure black kills the "Obsidian" depth.
*   **Don't** use 100% white text. Always use `on-surface` (#e0e5f6) to reduce eye strain in professional dark mode environments.
*   **Don't** use standard `md` (0.75rem) radii for large containers. In this system, "Modern" equals "Soft," so lean into `xl` (1.5rem) for all major surfaces.