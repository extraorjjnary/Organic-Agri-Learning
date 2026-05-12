# Neon Scholastic Design System

## 1. Overview & Creative North Star
The **Neon Scholastic** system is a high-energy, editorial-inspired framework designed for academic administration that avoids the "stale institution" trope. 

**Creative North Star: The Electric Archive.**
This system combines the precision of a scientific journal with the vibrant energy of modern tech. It uses a hyper-saturated "Neon Lime" (Primary) against a stark, sophisticated neutral palette to create immediate focus. The layout breaks the grid through high-contrast typography and intentional whitespace, treating administrative data like a curated exhibition rather than a simple spreadsheet.

## 2. Colors
Our color philosophy centers on the contrast between the "Seed" vitality and "Slate" stability.

- **The "No-Line" Rule:** Sectioning is achieved through color blocking (e.g., `#f6f8f6` backgrounds against `#ffffff` cards). Avoid 1px borders between major sections; use them only for internal table data or very tight component groupings where tonal shifts are insufficient.
- **Surface Hierarchy & Nesting:** Use `surface_container_lowest` (Pure White) for the primary interactive cards and `surface_container` for secondary background areas like search bars or sidebars. 
- **The "Neon Pop" Rule:** The primary color (#5bec13) is reserved for high-intent actions. In dark mode, this color should utilize a glow or "bloom" effect via `shadow-primary/20`.
- **Signature Textures:** Use `primary/20` (low opacity) for large iconography backgrounds or status chips to maintain the brand identity without overwhelming the user's cognitive load.

## 3. Typography
Neon Scholastic uses **Lexend** across all roles to leverage its hyper-legibility and geometric friendliness.

- **Typography Scale:**
    - **Display/Headline (1.875rem / 30px):** Black (900) weight, tracking-tight. Used for page titles to establish a "Header One" editorial presence.
    - **Titles (1.125rem / 18px):** Bold (700). Used for card headings and subject names.
    - **Body (0.875rem / 14px):** Regular (400). The workhorse for metadata and descriptions.
    - **Labels/Caption (0.75rem / 12px):** Semibold (600) for button text or Medium (500) for table headers, usually transformed to uppercase with tracking-wider.

The rhythmic shift from the massive 1.875rem headings to the tight 0.75rem labels creates a professional, authoritative hierarchy.

## 4. Elevation & Depth
Depth is communicated through light and shadow rather than structural lines.

- **The Layering Principle:** Main content exists on `surface_container_lowest`. The Sidebar and Header sit on a slightly different plane, separated by a single-side `outline_variant` border (border-r or border-b).
- **Ambient Shadows:** 
    - **`shadow-sm`:** Used for the main data table container to lift it slightly from the background.
    - **`shadow-lg` (Primary):** Used specifically for the "Add" button, creating a neon "halo" effect (`shadow-primary/20`) that suggests floating importance.
- **Glassmorphism:** For overlays or dropdown menus, use a backdrop blur (12px) with a semi-transparent `surface_bright` background.

## 5. Components
- **Buttons:** Primary buttons use `primary` fill with `on_primary` (black) text for maximum legibility. All buttons use `rounded-xl` (0.75rem) or `rounded-full`.
- **Status Chips:** Utilize `primary/20` background with `on_surface` text. This provides a "soft-high-vis" look that identifies active status without the harshness of a solid green block.
- **Input Fields:** Search bars should be `rounded-xl` and use `surface_container` as a fill color rather than a white background with a border.
- **Data Tables:** Remove all vertical borders. Use horizontal dividers (`divide-slate-100`) and a subtle `hover:bg-slate-50/50` transition to guide the eye.

## 6. Do's and Don'ts
- **Do:** Use large, bold icons in light-tinted boxes (`bg-blue-100`) to categorize data visually.
- **Do:** Ensure a minimum of 2rem (32px) padding for main page content to maintain an editorial feel.
- **Don't:** Use the primary color for text except for very specific status highlights or links; its high luminosity makes it difficult to read on white backgrounds.
- **Don't:** Use sharp corners. The system requires a minimum of `rounded-lg` for all components to maintain a modern, approachable aesthetic.