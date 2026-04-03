# Design System Document: The Editorial Hearth

This design system is a bespoke framework crafted for a high-end Mexican culinary experience. It moves away from the vibrant, high-energy tropes of casual dining and instead embraces the "Moody Gastronomy" aesthetic—focusing on dramatic tension, rich materiality, and the warmth of a flickering hearth.

## 1. Overview & Creative North Star

**Creative North Star: The Noir Hacienda**
The Noir Hacienda is an approach that treats the digital interface like a high-end lifestyle magazine or an architectural portfolio. We reject the "app-like" rigidity of standard grids in favor of a sophisticated, editorial layout.

**The Design Philosophy:**
*   **Intentional Asymmetry:** Break the expected centered alignment. Large typography should bleed off-center, and imagery should feel curated, not "placeholder."
*   **Tonal Depth:** We do not use "flat" layouts. We use light as a material, creating focus through glowing accents against a deep, infinite background.
*   **The "Bistro" Tension:** The pairing of an authoritative, high-contrast serif with a whisper-quiet, functional sans-serif creates a sense of luxury and precision.

## 2. Colors

The palette is designed to evoke charcoal, embers, and agave honey. We leverage Material Design 3 logic but apply it with an editorial eye.

### Palette Strategy
*   **The "No-Line" Rule:** Explicitly prohibit 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background is the only way to denote a change in content.
*   **Surface Hierarchy & Nesting:** Treat the UI as a series of physical layers.
    *   `surface` (#131313) is your base ground.
    *   `surface-container-lowest` (#0e0e0e) is used for "sunken" elements like footer areas.
    *   `surface-container-highest` (#353535) is used for "lifted" interactive cards.
*   **The "Glass & Gradient" Rule:** Use `surface-variant` with a 60% opacity and a `20px backdrop-blur` for navigation bars and floating overlays. 
*   **Signature Textures:** For primary buttons and Hero CTAs, use a subtle radial gradient: `linear-gradient(135deg, #ffb59c 0%, #c1440e 100%)`. This adds a "soulful glow" that flat hex codes lack.

## 3. Typography

The typography scale is designed for dramatic hierarchy, emphasizing the "High-End Bistro" feel.

*   **Display & Headlines (Noto Serif):** These are your "Signature" moments. Use `display-lg` for hero statements and `headline-lg` for section headers. The serif should feel heavy, prestigious, and slightly imposing.
*   **Body & Titles (Manrope):** The functional engine of the system. Manrope provides a clean, technical contrast to the serif. Keep `body-md` for descriptions to ensure readability against the dark background.
*   **Labeling:** Use `label-md` in all-caps with a `0.05em` letter-spacing for category tags (e.g., "APPETIZERS," "RESERVATIONS").

## 4. Elevation & Depth

We convey importance through **Tonal Layering** rather than structural lines or heavy drop shadows.

*   **The Layering Principle:** Depth is achieved by stacking tiers. To lift an element, move up the surface-container scale (e.g., a `surface-container-high` card on a `surface-container-low` background).
*   **Ambient Shadows:** If a floating effect is required (e.g., a mobile menu), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow must feel like an absence of light, not a black smudge.
*   **The "Ghost Border" Fallback:** If a boundary is strictly required for accessibility, use the `outline-variant` (#59413a) at 15% opacity. It should be felt, not seen.
*   **Glassmorphism:** Use semi-transparent layers for any element that floats over food photography. This allows the "warmth" of the food to bleed through the UI, maintaining the "appetizing" vibe.

## 5. Components

### Buttons
*   **Primary:** Uses the Burnt Orange gradient (`primary_container`). Border radius: `md` (0.375rem). Type: `title-sm` in `on_primary_container`.
*   **Secondary:** Ghost style. No fill. `outline` color for the label. Only a "Ghost Border" (20% opacity) on hover.
*   **Tertiary:** Warm Gold (`secondary`) text only. No container. Used for "View Menu" or less urgent actions.

### Cards (The Menu Item)
*   **Construction:** Use `surface-container-low`. Strictly **no dividers**. 
*   **Layout:** Use vertical white space (24px - 32px) to separate the item name from the description.
*   **Imagery:** Images should have a subtle inner-glow or "vignette" to blend into the charcoal background.

### Input Fields
*   **Style:** Underline-only or subtle "filled" style using `surface-container-high`. Avoid the "boxed" look. 
*   **Focus State:** The underline transitions to Warm Gold (`secondary`).

### Signature Component: The "Chef’s Highlight" Chip
*   A small, elegant element using `secondary_fixed` (#ffdfa0) with `on_secondary_fixed` (#261a00) text. Used sparingly to highlight "House Specialties" or "Limited Time" pairings.

## 6. Do's and Don'ts

### Do:
*   **Use High-Contrast Scaling:** Make your headers very large and your body text elegantly small. 
*   **Embrace Negative Space:** Let the "Deep Charcoal" breathe. Dark space is luxury space.
*   **Use Warm Gold for Precision:** Use `secondary` (#f6be39) only for the most important interactive cues or small decorative accents (like a star rating or a price).

### Don't:
*   **Don't use pure white:** Never use #FFFFFF. Always use `on_surface` (#e5e2e1) or `tertiary` to maintain the "moody" atmosphere.
*   **Don't use 1px Dividers:** Use a 40px gap or a background color shift instead. Lines feel like a spreadsheet; space feels like a gallery.
*   **Don't use "Cheerful" Animations:** Avoid bouncy or "pop" transitions. Use slow, sophisticated "fades" and "slides" (300ms–500ms) to mirror the pace of a fine dining experience.