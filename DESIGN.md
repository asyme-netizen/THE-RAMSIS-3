# Design System Strategy: The Editorial Authority

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Broadsheet."** 

This system rejects the "app-like" aesthetics of rounded corners and heavy shadows in favor of the architectural rigor of traditional print journalism. It is designed to feel like a high-end physical publication that has been flawlessly digitized. We move beyond generic templates by utilizing **intentional asymmetry**—where whitespace is treated as a structural element—and **tonal depth**, where content importance is communicated through subtle shifts in paper hue rather than aggressive borders. 

The goal is a signature visual identity that feels authoritative, intellectual, and premium. We achieve this by balancing the "ink" of high-contrast serif typography against the "breath" of an expansive, grid-based layout.

---

## 2. Colors
Our palette is a sophisticated interplay of high-contrast "Ink" and "Paper" tones, punctuated by a singular, aggressive "Journalism Red" accent.

### The Palette
- **Primary (Journalism Red):** `#91000e` — Used sparingly for urgency, breaking news, and primary CTAs.
- **Surface (Paper):** `#f9f9f9` — The base sheet.
- **On-Surface (Ink):** `#1a1c1c` — The primary medium for all long-form text.
- **Tertiary (Royal Deep):** `#00487d` — Used for secondary editorial categories (e.g., Opinion or Finance).

### The "No-Line" Rule
To maintain a high-end editorial feel, **1px solid borders are strictly prohibited for sectioning.** We define boundaries through background color shifts.
- A secondary article feed should sit on `surface-container-low` (`#f3f3f3`) to distinguish it from the `surface` (`#f9f9f9`) hero section.
- Content blocks are separated by generous vertical whitespace (`spacing-12` or `spacing-16`) rather than horizontal rules.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked sheets of fine paper. 
- **Base Layer:** `surface` (`#f9f9f9`).
- **Secondary Modules:** `surface-container` (`#eeeeee`).
- **High-Priority Insets:** `surface-container-highest` (`#e2e2e2`).
This nesting creates "soft" containment that guides the eye without the visual clutter of structural lines.

### Glass & Gradient Rule
For the main navigation bar and "Read More" overlays, use a **Glassmorphism** effect:
- Background: `surface` at 80% opacity with a `20px` backdrop-blur. 
- This allows the rich editorial imagery to bleed through, softening the transition between sections. 
- For CTAs, use a subtle linear gradient from `primary` (`#91000e`) to `primary-container` (`#b71c1f`) at a 135-degree angle to provide "soul" and depth to the red.

---

## 3. Typography
Typography is the voice of this system. We use a high-contrast pairing to distinguish between the "Story" and the "Data."

- **The Serif (Newsreader):** Our "Voice of Record." Used for `display` and `headline` scales. It should feel literary and intentional. Use `display-lg` (3.5rem) for hero features to command immediate attention.
- **The Sans (Work Sans):** Our "Utility." Used for `body` and `title` scales. It offers high legibility for long-form reading.
- **The Functional Sans (Public Sans):** Used for `label` scales. This is for metadata (timestamps, bylines, tags).

**Hierarchy Strategy:** 
- Use **tight letter-spacing** (-2%) for `display-lg` to give it a "custom-set" headline look.
- Use **generous line-height** (1.6) for `body-lg` to mimic the comfortable reading experience of a premium magazine.

---

## 4. Elevation & Depth
In this design system, "elevation" is a function of light and tone, not physical height.

- **The Layering Principle:** Depth is achieved by "stacking" surface tiers. Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a soft, natural lift.
- **Ambient Shadows:** For floating elements (like a newsletter pop-over), use "Ambient Shadows":
    - Blur: `40px` | Opacity: `6%` | Color: Derived from `on-surface` (`#1a1c1c`).
    - This mimics natural light falling on a stack of paper.
- **The Ghost Border Fallback:** If a border is required for accessibility (e.g., in high-contrast modes), use a "Ghost Border": `outline-variant` (`#e4beb9`) at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Article Cards & Lists
- **Forbid dividers.** Separate card items using `spacing-6` or `spacing-8`. 
- **The "Lead" Card:** Features a `display-sm` headline over a `surface-container-lowest` background. 
- **The "Brief" List:** Uses `on-surface-variant` for subheaders to create a clear tonal distinction from the primary headline.

### Buttons
- **Roundedness:** `0px` (Strictly Square).
- **Primary:** `primary` background with `on-primary` text. High-contrast, no shadow.
- **Tertiary:** Text-only with a `primary` underline that appears on hover.

### The Reading Interface
- **The Masthead:** A large, centered typographic mark using `display-lg`. It shrinks to a minimal glassmorphic bar upon scrolling.
- **Focus Mode:** In article view, the background shifts to `surface-container-lowest` (`#ffffff`) to maximize contrast and reduce eye strain, while the sidebar utilizes `surface-container-low` (`#f3f3f3`).

### Chips (Category Tags)
- **Style:** Square edges. Background: `surface-container-high`. Text: `label-md`. 
- **Interaction:** On hover, the background shifts to `primary` and the text to `on-primary`.

---

## 6. Do's and Don'ts

### Do:
- **Use the Grid for Asymmetry:** Place a main story across 8 columns and leave 4 columns of "White Space" (empty `surface` color) to create a premium, gallery-like feel.
- **Embrace Tonal Layering:** Use the `surface-container` tokens to group related content.
- **Prioritize Typographic Scale:** Let the size of the font, rather than its weight or color, dictate the hierarchy.

### Don't:
- **No Rounded Corners:** Do not use the `md`, `lg`, or `full` rounding tokens. Every component must be sharp (`0px`).
- **No Dividers:** Avoid `1px` lines between articles. Use `spacing-10` to create a "gutters of a newspaper" effect.
- **No Generic Shadows:** Never use the default "Drop Shadow" in your design tool. Always use the Ambient Shadow formula (low opacity, high blur).
- **No Flat Red Walls:** Avoid large blocks of solid `primary` red; use it for accents, underlines, and critical CTAs to maintain its impact.