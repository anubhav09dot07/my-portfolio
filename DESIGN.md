# Design System: High-End Editorial Portfolio

## 1. Overview & Creative North Star

**Creative North Star: "The Digital Curator"**
This design system is not a template; it is a gallery space. Inspired by high-end editorial design and avant-garde Japanese minimalism, "The Digital Curator" treats every pixel as a deliberate choice. We move away from the "busy" web by embracing **intentional asymmetry**, **extreme typographic scale**, and **tonal depth**.

The goal is to create an experience that feels "silent" yet powerful. By utilizing a monochromatic palette and removing traditional structural markers (like borders and hard shadows), we force the user to focus on the content—the photography, the typography, and the motion. This system breaks the rigid grid through "Floating Composition," where elements overlap or drift slightly off-center to create a sense of organic luxury.

---

## 2. Colors & Surface Philosophy

The palette is a sophisticated monochrome, utilizing Material Design 3 naming conventions to define a hierarchy of darks and greys.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1-pixel solid borders for sectioning or containment. 
*   **How to define boundaries:** Use background color shifts. A `surface-container-low` section sitting on a `surface` background creates a clear but soft boundary. 
*   **The Depth Stack:** Use `surface-container-lowest` (#0e0e0e) for the deep background and `surface-container-high` (#2a2a2a) for interactive elements to create natural, non-linear separation.

### Signature Textures & Glass
To avoid a flat "Bootstrap" feel, apply these treatments:
*   **Glassmorphism:** For floating navigation or modals, use `surface` with an 80% opacity and a `20px` backdrop-blur.
*   **The Tonal Gradient:** For primary CTAs or hero backgrounds, use a subtle linear gradient from `primary` (#c7c6c6) to `primary-container` (#919191) at a 135-degree angle. This adds "soul" and a metallic, premium finish.

---

## 3. Typography: Editorial Authority

The system uses a pairing of **Epilogue** for high-impact displays and **Manrope** for technical clarity.

*   **Display-LG (Epilogue, 3.5rem):** Use for hero statements. Set with `letter-spacing: -0.04em` and `font-weight: 200` to mimic high-fashion mastheads.
*   **Headline-MD (Epilogue, 1.75rem):** Reserved for project titles. Should be set in sentence case to feel approachable yet curated.
*   **Body-MD (Manrope, 0.875rem):** The workhorse. Increase line-height to `1.6` to ensure the "whitespace" flows through the text itself.
*   **Label-SM (Manrope, 0.6875rem):** Used for metadata (Year, Role, Category). Always uppercase with `letter-spacing: 0.1em` for a "technical" luxury aesthetic.

---

## 4. Elevation & Depth: Tonal Layering

Traditional shadows are replaced by **Ambient Occlusion** and **Tonal Stacking**.

*   **The Layering Principle:** Depth is achieved by stacking. Place a `surface-container-lowest` card on a `surface-container-low` section. The slight shift in hex value creates a "soft lift" that feels architectural rather than digital.
*   **Ambient Shadows:** If an element must float (e.g., a lightbox), use a shadow with a `40px` blur, `0%` spread, and `on-surface` color at `6%` opacity. This mimics natural light falling on a matte surface.
*   **The Ghost Border Fallback:** If accessibility requires a border, use the `outline-variant` token at `15%` opacity. This "Ghost Border" provides a hint of structure without interrupting the visual flow.

---

## 5. Components

### Hero Sections
Avoid centered layouts. Use a 12-column grid but place the `display-lg` text across columns 1-8, and the `body-lg` descriptive text in columns 9-12, shifted down by `spacing-12` (4rem). This intentional asymmetry signals high-end design.

### Project Grids (Cards)
*   **Forbid Divider Lines:** Separate projects using `spacing-20` (7rem) of vertical whitespace.
*   **The Hover Shift:** On hover, the image should subtly scale (1.02x) while the background shifts from `surface-container` to `surface-bright`.
*   **Metadata:** Place `label-md` tags at the bottom-left of images, using `on-surface-variant` color.

### Buttons
*   **Primary:** A pill-shape (`rounded-full`) using the `primary` background and `on-primary` text. No border.
*   **Secondary (The Underline):** No background. Use `title-sm` text with a 1px underline that expands from the center on hover.
*   **Tertiary:** `label-md` text only, with a `0.5` opacity that shifts to `1.0` on hover.

### Integrated Social Links
Social links should not use brand colors (e.g., no "Twitter Blue"). They must remain monochromatic. Use `outline-variant` icons that transition to `primary` upon interaction. Place them in a fixed vertical orientation on the right-hand side of the viewport to act as a "framing" element.

### Input Fields
*   **Styling:** Only a bottom border using `outline-variant`. 
*   **Focus State:** The bottom border transforms into a `primary` color bar (2px), and the label floats upward using `label-sm` styles.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use extreme whitespace. If a section feels finished, add another `spacing-10` of padding.
*   **Do** use "Staggered Entry" animations. Elements should fade and slide up in a sequence (20ms delay between items).
*   **Do** lean into monochromatic contrast. Use `#FFFFFF` text on a `#0e0e0e` background for high-impact statements.

### Don't
*   **Don't** use 1px borders to separate content blocks. Use the Spacing Scale or Tonal Layering.
*   **Don't** use standard easing. Use `cubic-bezier(0.23, 1, 0.32, 1)` (the "Expo Out" feel) for all transitions to achieve a "luxury" motion feel.
*   **Don't** use more than one accent color. If you use a color outside the monochrome scale, it must be used for exactly one purpose (e.g., active status indicators only).

### Accessibility Note
While we prioritize minimalism, ensure that contrast ratios between `on-surface` and `surface` maintain a minimum of 4.5:1 for body text. Use `outline` tokens for keyboard focus states to ensure the "No-Line" rule does not compromise navigability.