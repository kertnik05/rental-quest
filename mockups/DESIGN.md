# Design System Specification: High-End Property Management

## 1. Overview & Creative North Star
This design system moves away from the "utility-only" aesthetic of traditional property management software and toward a **"Sophisticated Concierge"** experience. 

**Creative North Star: The Architectural Editorial.**
The interface should feel like a high-end architectural magazine—structured, airy, and authoritative. We achieve this by rejecting the "boxed-in" layout of standard mobile apps in favor of **Tonal Layering** and **Intentional Asymmetry**. Instead of rigid grids, we use white space as a structural element, allowing financial data to breathe and "floating" high-priority cards to guide the user's eye through a logical narrative of their properties.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule
The palette is rooted in a deep, authoritative navy, balanced by soft, atmospheric neutrals. 

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section off content. Physical boundaries must be defined solely through background color shifts or subtle tonal transitions. For example, a `surface-container-low` section sitting on a `surface` background creates a clear but sophisticated division that a border cannot replicate.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine vellum.
*   **Base:** `surface` (#faf9fd) for the overall screen background.
*   **Secondary Content:** `surface-container-low` (#f4f3f7) for grouping related data.
*   **Interactive Cards:** `surface-container-lowest` (#ffffff) to provide the "cleanest" white for high-readability financial data.

### Signature Textures & Glassmorphism
*   **The Glass Rule:** For floating navigation bars or high-priority "Today" alerts, use `surface` at 80% opacity with a `20px` backdrop-blur. This allows the property photos or data underneath to bleed through, softening the edges.
*   **Subtle Gradients:** Main Action CTAs (Primary) should utilize a subtle vertical gradient from `primary_container` (#1a365d) at the top to `primary` (#002045) at the bottom. This adds "visual soul" and a premium weight to the interaction.

---

## 3. Typography: The Editorial Scale
We pair **Manrope** (a modern geometric sans with high legibility) for headers with **Inter** for data-heavy body text.

*   **Display & Headlines (Manrope):** Use `display-md` (2.75rem) for high-level portfolio totals. The generous tracking and geometric curves of Manrope convey a sense of modern "Property Tech" luxury.
*   **Titles & Body (Inter):** Use `title-md` (1.125rem) for property names. Inter’s tall x-height ensures that complex financial figures and rental dates remain legible at small mobile scales.
*   **Hierarchy Note:** High-contrast typography is key. Pair a `headline-sm` title in `on_surface` with a `label-sm` subtitle in `on_surface_variant` to create immediate scannability without needing dividers.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows and borders are replaced by a system of **Environmental Depth**.

*   **The Layering Principle:** Depth is achieved by "stacking." Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a soft, natural "lift" that mimics ambient light.
*   **Ambient Shadows:** If an element must float (e.g., a "New Maintenance Request" FAB), use an extra-diffused shadow: `Offset: 0, 12; Blur: 24; Color: 4% opacity of on_surface`. Never use pure black shadows; always tint them with the `on_surface` tone.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use `outline_variant` at **15% opacity**. High-contrast, 100% opaque borders are strictly forbidden as they clutter the visual field.

---

## 5. Components

### Cards & Action Items
*   **The Signature Card:** Use `xl` (1.5rem) rounded corners. Cards must never have borders. Use `surface-container-lowest` for the card body against a `surface-container` background.
*   **Layout:** Forbid divider lines within cards. Use `spacing-6` (1.5rem) to separate internal content blocks.

### Primary Buttons
*   **Visuals:** `full` (9999px) rounded corners (pill-shaped). Use the Primary-to-Primary-Container gradient. 
*   **Typography:** `label-md` in Bold, all-caps with 0.05rem letter spacing for an "authoritative" feel.

### Input Fields
*   **Style:** Background-filled using `surface-container-high`. No bottom border.
*   **Focus State:** Shift background to `surface-container-highest` and add a subtle 2px "Ghost Border" using `primary` at 20% opacity.

### Status Chips
*   **Payment Success:** `secondary_container` (#86f2e4) background with `on_secondary_container` (#006f66) text.
*   **Alert/Overdue:** `tertiary_fixed` (#ffdcc3) background with `on_tertiary_fixed_variant` (#6e3900) text.

### Relevant App Components
*   **Financial Snapshot Widget:** A `surface-container-lowest` card with a `3.5rem` display value. Use a subtle `secondary` (#006a61) "sparkline" graph to show growth trends without bulky axes.
*   **The "Today" Stack:** Vertically stacked cards using `spacing-4` (1rem). The top card should use a 5% larger scale than the ones below it to imply a physical deck of tasks.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical padding (e.g., more top padding than bottom) in headers to create an editorial feel.
*   **Do** use `secondary` (Teal) sparingly to draw attention to "Growth" or "Success" metrics.
*   **Do** ensure all financial data is set in Inter for maximum clarity.

### Don’t
*   **Don’t** use 1px dividers. If you need to separate content, use `0.5rem` or `1rem` of white space.
*   **Don’t** use standard "Material Design Blue." Stick to the Deep Navy (`primary`) to maintain the "RentalQuest" sense of premium trust.
*   **Don’t** use sharp corners. The `DEFAULT` (0.5rem) is the minimum; lean toward `lg` (1rem) for most interactive containers.