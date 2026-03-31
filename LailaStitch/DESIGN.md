# Design System Specification: The Algorithmic Atelier

## 1. Overview & Creative North Star: "Precision Organicism"
The creative direction for this design system is **Precision Organicism**. While the core of an AI consultancy is data and logic, the brand "Arete" (meaning excellence and virtue) demands a human-centric, high-end editorial execution. We move away from the "boxy" SaaS aesthetics by utilizing intentional asymmetry, expansive negative space, and a layering logic that mimics complex neural networks.

The "template" look is strictly forbidden. Instead of rigid grids, we use **overlapping editorial layouts** where typography breaks container boundaries and glassmorphism creates a sense of "digital depth." This system feels like a high-end physical portfolio transformed into a liquid, high-tech interface.

---

## 2. Colors & Surface Logic
The palette balances the deep, authoritative greens and oranges of the brand profile with a clinical, high-tech slate environment.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Structural boundaries must be defined solely through background color shifts or tonal transitions.
- Use `surface-container-low` (#f6f3ee) for large background sections.
- Use `surface-container-lowest` (#ffffff) for primary content modules.
- The eye should perceive change through "slight shifts in light," not artificial lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Each "inner" container should use a tier to define importance:
- **Base Layer:** `surface` (#fcf9f4)
- **Secondary Section:** `surface-container-low` (#f6f3ee)
- **Actionable Cards:** `surface-container-lowest` (#ffffff)
- **Contextual Overlays:** `surface-bright` with 80% opacity and a 20px backdrop-blur.

### The "Glass & Gradient" Rule
To capture the "AI neural network" feel, use **Glassmorphism** for floating navigational elements and modals. 
- **Signature Gradient:** Transition from `primary` (#1d5328) to `primary-container` (#366c3e) at a 135-degree angle for hero buttons and primary CTAs. This adds a "lithographic" depth that flat colors lack.

---

## 3. Typography
We utilize a sophisticated pairing of **Inter** for data-driven clarity and **Cormorant Garamond** (interpreted through Inter's high-scale display weights) for editorial authority.

*   **Display (L/M/S):** Inter Bold. Used for high-impact value propositions. Tracking should be set to -0.02em to feel "tight" and engineered.
*   **Headline (L/M/S):** Inter SemiBold. Reserved for section titles. This provides the "modern sans-serif" high-tech feel requested.
*   **Title (L/M/S):** Inter Medium. For card titles and secondary navigation.
*   **Body (L/M/S):** Inter Regular. The workhorse for consultation details. The line height should be generous (1.6) to ensure readability against the light backgrounds.
*   **Label (M/S):** Inter All-Caps. Used for "AI Status" indicators or technical metadata, mimicking a command-line aesthetic.

---

## 4. Elevation & Depth
Hierarchy is achieved through **Tonal Layering** rather than drop shadows.

*   **The Layering Principle:** Place a `surface-container-lowest` card on top of a `surface-container-low` background. This creates a "soft lift" that feels architectural.
*   **Ambient Shadows:** For floating elements (like an AI Chatbot UI), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(29, 83, 40, 0.05)`. This uses a tinted version of the `primary` color to mimic natural light filtering through digital glass.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` (#c1c9bd) at **15% opacity**. Never use a 100% opaque border.
*   **Backdrop Blur:** All glass elements must utilize a `backdrop-filter: blur(12px)`. This ensures that as users scroll, the "neural network" of the content below stays visible but softened.

---

## 5. Components

### Buttons
*   **Primary:** A subtle gradient (`primary` to `primary-container`). Roundedness `full` (9999px) to convey the "approachable" feel.
*   **Secondary:** `surface-container-lowest` with a "Ghost Border."
*   **Tertiary:** Text-only in `primary` with an arrow icon that shifts 4px on hover.

### Cards & Lists
*   **The Rule:** **Strictly forbid divider lines.** 
*   Separate list items using `spacing-4` (1rem) of vertical whitespace or by alternating background colors between `surface-container-lowest` and `surface-container-low`.
*   Cards should use `rounded-xl` (1.5rem) to feel friendly and modern.

### Input Fields
*   **Style:** Minimalist. No bottom line or full border. Use a `surface-container-highest` background with a `rounded-md` (0.75rem). On focus, transition the background to `surface-bright` and add a 1px "Ghost Border" using `secondary` (#944a00) at 20% opacity.

### AI Progress Indicators (Custom Component)
*   Instead of a standard spinner, use a pulsing "aura" utilizing `secondary-container` (#fc8f34) with a large blur radius. This represents "Growth" and "Processing" in a non-mechanical way.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical margins. If the left margin is `spacing-12`, try a `spacing-24` right margin for editorial impact.
*   **Do** allow images of neural networks or data visualizations to "bleed" off the edge of the screen.
*   **Do** use `primary-fixed` (#b5f1b7) for highlighting key "Growth" metrics in data visualizations.

### Don't
*   **Don't** use pure black (#000000) for text. Always use `on-surface` (#1c1c19) to maintain the organic feel.
*   **Don't** use standard "drop shadows" on cards. Stick to tonal layering or the Ambient Shadow spec.
*   **Don't** use sharp 90-degree corners. Even for "high-tech" elements, the minimum roundedness should be `sm` (0.25rem).