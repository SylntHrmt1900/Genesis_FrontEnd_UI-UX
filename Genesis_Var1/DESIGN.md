# Design System Specification: Genesis

## 1. Overview & Creative North Star: "The Luminous Horizon"
This design system rejects the "flat and boxy" aesthetic of traditional SaaS. Instead, it embraces a Creative North Star titled **"The Luminous Horizon."** 

The objective is to create a digital environment that feels like a physical space illuminated by soft, indirect light. We move beyond "standard" UI by prioritizing **tonal depth over structural lines**. By utilizing intentional asymmetry, overlapping layers, and high-contrast typography scales, Genesis feels less like a tool and more like a high-end editorial experience. It is clean and professional, yet possesses an "organic soul" through soft gradients and glassmorphism.

---

### 2. Colors & Surface Philosophy
The palette is rooted in deep indigo and slate, using a "Soft Dark" approach that avoids pure blacks to reduce eye strain and increase the perceived "depth" of the screen.

#### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are prohibited for sectioning. Boundaries must be defined solely through background color shifts or subtle tonal transitions.
- **Example:** A sidebar (`surface_container_low`) sitting against the main content area (`surface`) creates a clear but soft boundary without a harsh line.

#### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, frosted layers. Use the following tokens to define importance:
- **Base Layer:** `surface` (#060e20)
- **Secondary Sectioning:** `surface_container_low` (#06122c)
- **Interactive Components/Cards:** `surface_container` (#0a1836)
- **Elevated Modals/Popovers:** `surface_container_highest` (#11244c)

#### The "Glass & Gradient" Rule
To elevate the "Soft Tech" feel, use **Glassmorphism** for floating elements (Top Nav, Floating Action Buttons). 
- **Recipe:** Fill: `surface_variant` at 60% opacity + Backdrop Blur: 20px.
- **Signature Textures:** For primary CTAs, use a subtle linear gradient (45°) from `primary` (#bdc2ff) to `primary_container` (#3c47af) to provide a "glow" that flat colors cannot achieve.

---

### 3. Typography
Genesis uses a dual-sans approach to balance editorial authority with functional clarity.

| Level | Font | Size | Token | Intent |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | Manrope | 3.5rem | `display-lg` | Hero moments; high-impact "Big Idea" text. |
| **Headline**| Manrope | 2rem | `headline-lg` | Section headers; sets the editorial tone. |
| **Title**   | Inter | 1.125rem| `title-md` | Card titles and navigation headers. |
| **Body**    | Inter | 1rem | `body-lg` | Primary reading content; high legibility. |
| **Label**   | Inter | 0.75rem | `label-md` | Micro-copy and utility metadata. |

**The Typography Strategy:** Use `Manrope` for headers to provide a "technical yet round" personality. Switch to `Inter` for body text to ensure maximum readability in data-heavy environments. Always maintain generous line-height (1.6x for body) to honor the "Soft Tech" personality.

---

### 4. Elevation & Depth
In this design system, shadows are light, and layers are logical.

- **The Layering Principle:** Depth is achieved by "stacking" surface tiers. Place a `surface_container_lowest` card on a `surface_container_low` section to create a soft, natural "lift."
- **Ambient Shadows:** When a floating effect is required (e.g., a dropdown), shadows must be extra-diffused.
    - **Shadow Token:** `0px 24px 48px rgba(0, 0, 0, 0.4)`. 
    - **Tinting:** Shadows should never be pure grey. Use a hint of the `on_surface` color to mimic ambient light.
- **The "Ghost Border" Fallback:** If a border is legally or accessibly required, use `outline_variant` at **20% opacity**. 100% opaque borders are strictly forbidden.
- **Roundedness Scale:**
    - **Default:** `1rem` (16px) - The standard for all cards and containers.
    - **Sm:** `0.5rem` (8px) - For small components like tags or inputs.
    - **Full:** `9999px` - Reserved for Pills and Circular Buttons.

---

### 5. Components

#### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`). White text (`on_primary_fixed`). No border. `1rem` padding-x.
- **Secondary:** Surface fill (`surface_container_high`). Subtle `primary` text.
- **Tertiary:** Ghost style. No background. `primary` text. Use for low-emphasis actions.

#### Input Fields
- **Base Style:** Fill with `surface_container_low`. 
- **Shape:** `0.5rem` (8px) radius.
- **States:** On focus, transition the background to `surface_container` and add a "Ghost Border" using the `primary` color at 40% opacity. Avoid heavy glow effects.

#### Cards & Lists
- **The "No-Divider" Rule:** Forbid the use of divider lines between list items. Use vertical white space (token `6`: 2rem) or a subtle background shift on hover (`surface_variant`) to separate content. 
- **Layout:** Use asymmetrical padding (e.g., more padding on the top than the bottom) to give a custom, "designed" feel rather than a generated one.

#### Chips
- **Selection Chips:** Use `secondary_container` with `on_secondary_container` text. High-radius (`full`) for a pill shape.

---

### 6. Do’s and Don’ts

#### Do
- **Do** use `20` (7rem) spacing for major section breaks to create a feeling of luxury and "breath."
- **Do** use "Manrope" for numbers and data visualizations; its geometric nature feels premium.
- **Do** utilize `tertiary` (#c180ff) as a "spark" color—use it sparingly for notifications or "New" badges to break the blue/indigo monotony.

#### Don’t
- **Don’t** use a shadow and a border at the same time. Choose one method of separation.
- **Don’t** use pure white (`#FFFFFF`) for text. Use `on_surface` (#dee5ff) to maintain the "Soft Tech" atmosphere.
- **Don’t** crowd the interface. If a layout feels busy, increase the spacing scale by two increments.