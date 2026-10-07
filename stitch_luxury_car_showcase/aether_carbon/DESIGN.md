# Design System: High-End Automotive Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"Kinetic Velocity."** 

This is not a catalog; it is a digital gallery. To showcase luxury sports cars, we must move beyond the "grid-of-cards" template. The system utilizes a high-contrast dark environment where the UI recedes, allowing the photography to become the structural element. We achieve a premium feel through **intentional asymmetry**, where text elements are often offset to create a sense of movement, and **tonal depth**, where surfaces feel like layered obsidian and frosted glass.

## 2. Colors & Surface Philosophy
The palette is rooted in deep obsidian (`#131313`) and midnight blues, punctuated by "Electric Neon" (`#00daf3` and `#aed500`) to mimic the glow of high-performance instrumentation.

### The "No-Line" Rule
Traditional 1px borders are strictly prohibited for sectioning. They feel "cheap" and structural. Instead, define boundaries through:
*   **Tonal Shifts:** Transitioning from `surface` to `surface-container-low`.
*   **Negative Space:** Using expansive padding to let the eye identify groupings.
*   **Soft Gradients:** Using a subtle linear-gradient from `surface-container-low` to `surface-container-lowest` to define card regions.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of luxury materials.
*   **Base Layer:** `surface` (#131313) – The infinite dark void.
*   **Middle Layer:** `surface-container-low` – Used for subtle sectioning of technical specs.
*   **Top Layer (Interactive):** `surface-container-high` – Reserved for hover states or active selection containers.

### The "Glass & Gradient" Rule
To capture the "Neon & Glass" aesthetic, use `surface-variant` with a `backdrop-blur` of 20px for any floating navigation or modal elements. Main CTAs should not be flat; they should utilize a subtle 45-degree gradient from `primary` (#00daf3) to `on-primary-container` (#0091a2) to provide a "metallic" luster.

## 3. Typography
The typography system uses a "Tech-Luxury" pairing. 

*   **Display & Headlines (Space Grotesk):** This typeface provides a wide, technical, and aggressive stance reminiscent of automotive branding. Use `display-lg` for hero titles with a `letter-spacing` of -0.02em to make it feel "tight" and engineered.
*   **Body & Labels (Manrope):** A clean, geometric sans-serif that ensures readability against dark backgrounds. Manrope’s modern proportions keep the UI feeling "fresh" and approachable.

**Hierarchy Tip:** Always use `label-md` in uppercase with 0.1em tracking for technical specs (e.g., "0-60 MPH") to evoke the feel of a precision instrument cluster.

## 4. Elevation & Depth
In a dark theme, shadows must be handled with extreme delicacy to avoid "muddy" layouts.

*   **Tonal Layering:** Avoid shadows for static elements. Place a `surface-container-highest` card on a `surface` background to create a soft, natural "lift."
*   **Ambient Shadows:** For floating action buttons or high-priority modals, use a shadow with a 40px blur, 0% spread, and an opacity of 15% using the `on-surface` color. This creates a glow rather than a shadow.
*   **The "Ghost Border":** For input fields or subtle containment, use `outline-variant` (#44474e) at 20% opacity. This provides just enough edge definition for accessibility without breaking the "No-Line" rule.

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `on-primary-container`), roundedness `sm` (0.125rem) for a sharp, precision-cut look. No border.
*   **Secondary:** Glassmorphic fill. `surface-variant` at 40% opacity with `backdrop-blur`.
*   **Tertiary:** Text-only in `primary` color. Use for "Learn More" links with a custom underline animation.

### Glass Cards (Vehicle Specs)
*   **Background:** `surface-container-low` at 60% opacity.
*   **Effect:** `backdrop-filter: blur(12px)`.
*   **Corner Radius:** `lg` (0.5rem).
*   **Interaction:** On hover, shift background to `surface-container-high` and increase the blur.

### Navigation Rails
*   Instead of a top bar, use an asymmetrical side rail or a floating "Glass Dock" at the bottom using `surface-container-lowest` at 80% opacity.

### Input Fields
*   Minimalist style. No background fill. Use a `surface-variant` bottom-border (2px) that transforms into a `primary` neon glow upon focus.

### Lists & Specs
*   **Forbid Dividers:** Do not use lines between car specs. Use `body-md` for the label and `title-lg` for the value, separated by a 4px vertical gap and 24px of horizontal breathing room.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Place the car image off-center and let the text overlap the image slightly using `surface-variant` text for high contrast.
*   **Use Neon Accents Sparingly:** Reserve `tertiary` (#aed500) only for high-priority alerts or "In Stock" indicators.
*   **Animate "In-View":** Elements should slide in with a custom cubic-bezier (0.2, 0, 0, 1) to mimic the smooth acceleration of a sports car.

### Don't:
*   **Don't use white (#FFFFFF):** Use `on-surface` (#e5e2e1) for text. Pure white is too harsh on a `#131313` background and causes visual vibration.
*   **Don't use standard shadows:** Dark themes swallow shadows. Use color shifts or glass blurs instead.
*   **Don't crowd the canvas:** Luxury is defined by the space you *don't* fill. Every car model should have at least 120px of vertical padding between sections.