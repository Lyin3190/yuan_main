# Design System Strategy: The Ethereal Observer

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Greenhouse."** 

This is not a traditional flat UI; it is an atmospheric experience that mimics the quiet, observant clarity of a gentle rainy day. We move beyond the "template" look by treating the viewport as a pane of glass overlooking a misty landscape. To achieve a "tech-forward" yet "gentle" personality, we balance high-precision modern typography with organic, asymmetric layouts. Elements should feel like they are floating or resting on soft moss, rather than being locked into a rigid, industrial grid. 

Avoid "boxed-in" designs. Use wide margins, overlapping containers, and intentional white space to let the interface breathe. The goal is to make the user feel a sense of calm focus.

---

## 2. Colors: Tonal Atmosphere
The palette is a sophisticated gradient of Sage, Mint, and Cream. We do not use color to "decorate"—we use it to define environmental depth.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section off content. 
Boundaries must be defined solely through background color shifts. For instance, a `surface-container-low` (#f1f5f0) card should sit on a `surface` (#f8faf6) background. This creates a soft "ledge" effect that feels premium and intentional.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked sheets of fine, semi-translucent paper.
*   **Base:** `surface` (#f8faf6)
*   **Primary Containers:** `surface-container` (#eaefea)
*   **Elevated Details:** `surface-container-highest` (#dde4de)
*   **Floating Elements:** Use `surface-container-lowest` (#ffffff) to provide the brightest "pop" against darker sage backgrounds.

### The "Glass & Gradient" Rule
To evoke the "rainy day" aesthetic, use Glassmorphism for floating navigation bars and modals. Apply a `backdrop-filter: blur(12px)` to a semi-transparent version of `surface_bright`. 
*   **Signature Texture:** Main CTAs should utilize a subtle linear gradient from `primary` (#4b6648) to `primary_dim` (#3f5a3d) to provide a soft, velvet-like depth.

---

## 3. Typography: Elegant Precision
We use **Manrope** exclusively. It is a modern geometric sans-serif that retains a humanistic warmth, fitting our "tech-forward yet gentle" personality.

*   **Display & Headlines:** Use `display-lg` (3.5rem) and `headline-md` (1.75rem) with tighter letter-spacing (-0.02em) to create an editorial, high-fashion feel. Headlines should feel like "titles of a poem" rather than "labels for a box."
*   **Body:** `body-lg` (1rem) is the workhorse. Ensure line-height is generous (1.6) to maintain the "refreshing" and "airy" brand feel.
*   **Labels:** `label-md` (0.75rem) should be used sparingly for metadata, often in `on_surface_variant` (#5a615c) to reduce visual noise.

The hierarchy is built on extreme contrast: large, light-weighted headlines paired with small, precisely placed body text.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too "heavy" for a rainy-day theme. We use light and tone to imply height.

### The Layering Principle
Depth is achieved by "stacking" surface tiers. To create a "lifted" card:
1.  Place a `surface-container-lowest` (#ffffff) object on a `surface-container-low` (#f1f5f0) background.
2.  The 10-point difference in hex value provides enough contrast for the eye without creating a "hard" edge.

### Ambient Shadows
When a physical "float" is required (e.g., a FAB or Popover), use an **Extra-Diffused Shadow**:
*   `box-shadow: 0 12px 40px rgba(45, 52, 48, 0.06);` 
*   Note the use of the `on_surface` color (#2d3430) at a very low opacity (6%) rather than pure black. This mimics natural light passing through mist.

### The "Ghost Border" Fallback
If a border is legally or functionally required, use a "Ghost Border":
*   `outline_variant` (#acb4ae) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: The Soft Edge
All components utilize the Roundedness Scale, favoring `DEFAULT` (1rem) for containers and `full` for interactive elements.

*   **Buttons:**
    *   *Primary:* Gradient fill (`primary` to `primary_dim`), `on_primary` text, `full` rounding. 
    *   *Tertiary:* Ghost style. No background, just `primary` text. Use for low-priority actions.
*   **Input Fields:**
    *   Use `surface-container-high` (#e4eae4) as the fill. No bottom line. Use `md` (1.5rem) rounding to make the form feel approachable.
*   **Chips:**
    *   Filter chips should use `secondary-container` (#d1e9cc). When active, they transition to `primary` with `on_primary` text. 
*   **Cards & Lists:**
    *   **Strict Rule:** No dividers. Separate list items using the `Spacing Scale 3` (1rem) gap or a subtle background shift on hover to `surface-container-highest`.
*   **Floating Navigation:**
    *   A bottom-docked nav bar using Glassmorphism (`surface` at 70% opacity + blur) with `xl` (3rem) corner radius.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** embrace asymmetry. Align text to the left but place a decorative image or "rain-drop" element off-center to the right.
*   **Do** use `Spacing Scale 16` (5.5rem) or `20` (7rem) between major sections to emphasize the "refreshing" quality.
*   **Do** use `primary_container` (#ccebc5) for success states instead of harsh greens; it’s more on-brand.

### Don't:
*   **Don't** use pure black (#000000) for anything. Even for text, use `on_surface` (#2d3430).
*   **Don't** use sharp 90-degree corners. Everything must feel "water-worn" and smooth.
*   **Don't** clutter the screen. If a feature isn't essential, hide it behind a "More" action to maintain the "observant" and quiet atmosphere.
*   **Don't** use standard 1px dividers. If you must separate, use a wide gap or a change in surface tone.

---

*This design system is a living document. It should feel like a quiet conversation—gentle, clear, and sophisticated.*