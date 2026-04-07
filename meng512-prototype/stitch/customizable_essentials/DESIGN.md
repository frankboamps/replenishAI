# Design System Specification: The Proactive Curator

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Proactive Curator."** 

Most AI assistants feel like spreadsheets or chatbots; this system must feel like a premium concierge service. We move beyond the "utility app" aesthetic by embracing an editorial, high-end digital experience. The goal is to convey intelligence through silence—using vast amounts of negative space (whitespace), intentional asymmetry, and tonal depth to guide the user’s eye without "shouting" for attention.

By utilizing the "Proactive Curator" philosophy, we replace rigid, boxed-in grids with a fluid, layered interface. We break the "template" look by allowing elements to overlap slightly and by utilizing a typography scale that favors dramatic, authoritative headers contrasted against precise, functional body copy.

---

## 2. Color Philosophy
Our palette is rooted in a foundation of trust, but executed with sophisticated depth. We move away from flat UI by using a hierarchical system of surfaces.

### Surface Hierarchy & Nesting
To achieve a premium feel, we strictly follow the **"No-Line Rule."**
- **The Rule:** 1px solid borders are prohibited for sectioning. 
- **The Execution:** Boundaries must be defined by shifts in background color. For example, a `surface-container-low` (#f3f4f6) section should sit directly on a `surface` (#f8f9fb) background. 
- **Nesting Depth:** Use the surface-container tiers to create physical layers. Treat the UI as stacked sheets of fine paper. An inner card (`surface-container-lowest` / #ffffff) should "lift" off a `surface-container` (#edeef0) background purely through tonal contrast.

### The Glass & Gradient Rule
To ensure the AI feels "smart" and modern:
- **Glassmorphism:** Use semi-transparent surface colors with a `backdrop-filter: blur(20px)` for floating navigation bars or persistent status overlays.
- **Signature Textures:** Main CTAs and Hero sections should not be flat. Use a subtle linear gradient (Top-Left to Bottom-Right) transitioning from `primary` (#003d9b) to `primary_container` (#0052cc). This adds a "soul" to the brand that flat hex codes cannot provide.

---

## 3. Typography: The Editorial Voice
We use **Inter** as our typographic backbone. To achieve the "Curator" look, we use a high-contrast scale that mimics a modern lifestyle magazine.

*   **Display (Large/Medium):** Reserved for high-impact AI insights (e.g., "Your pantry is optimized."). These should use `display-lg` (3.5rem) with tight letter-spacing (-0.02em).
*   **Headlines:** Used for section titles. `headline-sm` (1.5rem) provides enough authority to lead a page without crowding the content.
*   **Body Copy:** All functional information stays in `body-md` (0.875rem). We prioritize legibility by using a generous line-height (1.6) to ensure the interface feels "breathable."
*   **Labels:** Use `label-md` (0.75rem) in all-caps with a slight letter-spacing (+0.05em) for category tags like "DAIRY" or "HOUSEHOLD."

---

## 4. Elevation & Depth
We define hierarchy through **Tonal Layering** rather than structural shadows.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-lowest` card placed on a `surface-container-low` background creates a soft, natural lift.
*   **Ambient Shadows:** If an element must float (like a modal or a floating action button), use an extra-diffused shadow. 
    *   *Value:* `0px 20px 40px rgba(25, 28, 30, 0.06)`. 
    *   *Note:* Never use pure black for shadows; always use a tinted version of `on_surface`.
*   **The Ghost Border Fallback:** If a boundary is strictly required for accessibility, use the "Ghost Border"—the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.

---

## 5. Signature Components

### Cards & Lists (The Replenishment Feed)
*   **Style:** No dividers. Separate items using `spacing-5` (1.7rem) of vertical whitespace.
*   **Logic:** A card containing a low-stock item should use a `tertiary_fixed` (#ffddb3) background to gently draw the eye without the "emergency" feel of a red error.

### Buttons (Intentional Actions)
*   **Primary:** Gradient fill (`primary` to `primary_container`), `rounded-md` (0.75rem), with `on_primary` (#ffffff) text.
*   **Secondary:** Ghost style. No fill, `outline_variant` at 20% opacity, text in `primary`.
*   **Interaction:** On hover, increase the `surface_tint` overlay by 8% to create a "glow" rather than a color change.

### Inventory Chips
*   **Selection:** Use `secondary_container` (#82f9be) for "In Stock" items.
*   **Warning:** Use `tertiary_container` (#7d5200) for "Low Stock" items.
*   **Style:** Rounded-full (9999px) to contrast against the geometric card shapes.

### Smart Input Fields
*   **Surface:** Use `surface_container_highest` (#e1e2e4) with no border. 
*   **State:** On focus, transition the background to `surface_container_lowest` (#ffffff) and add a subtle `primary` glow.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical layouts. Place a large headline on the left and a small supporting card shifted to the right to create an "editorial" flow.
*   **Do** leverage the `secondary` (#006c47) green for "Proactive Success" messages—it reinforces the AI’s helpfulness.
*   **Do** use `spacing-12` (4rem) for section padding to ensure the UI never feels "cramped."

### Don't:
*   **Don't** use 1px dividers between list items. Use background tonal shifts instead.
*   **Don't** use pure black (#000000). Use `on_surface` (#191c1e) for all text to maintain a premium, softer contrast.
*   **Don't** use hard corners. Every element should follow the `rounded-md` (0.75rem) or `rounded-lg` (1rem) standard to feel approachable.
*   **Don't** use aggressive animations. Transitions should be slow (300ms) and use "Standard Easing" (cubic-bezier(0.4, 0, 0.2, 1)).