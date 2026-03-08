

# AssetVault — Design Asset Manager

A single-page personal design asset manager with localStorage persistence, dark/light theme, and full CRUD + export functionality.

## Core Structure

- **Single-page app** with sidebar navigation, top navbar, and main content area
- **Dark theme by default** with purple accent (#7C3AED), deep dark backgrounds, and a light mode toggle persisted to localStorage
- **Inter font** throughout, responsive layout with mobile hamburger drawer

## Layout & Navigation

- **Top Navbar**: Logo "AssetVault", search bar (real-time debounced), "+ Add Asset" button, Grid/List view toggle, Palette Preview button, theme toggle
- **Left Sidebar**: "All Assets" with count, filter by type (Color/Font/Icon/Image) with counts, filter by project (dynamic) with counts, "+ New Project" button, delete project option
- **Main Content**: Filtered gallery of asset cards or list rows

## Asset Cards (4 types)

- **Color**: horizontal swatches, name, tags as pills, copy-hex on hover
- **Font**: rendered preview text in the font via Google Fonts, weight badges
- **Icon**: centered SVG render, copy SVG on hover
- **Image**: object-cover image with name overlay, open-in-new-tab on hover
- All cards show edit/delete icons on hover with scale animation

## Add/Edit Asset Modal

- Dynamic form: basic info (name, type selector, project dropdown with inline "new project" option, tag input)
- Type-specific fields appear based on selection: color picker rows, font family + weight checkboxes with live preview, SVG textarea with live preview, image URL with live preview
- Validation with inline errors, Save/Update and Cancel buttons

## Color Palette Previewer

- Modal/panel showing all color assets grouped by project as horizontal swatch strips with hex labels
- "Copy Hex" per swatch
- Export as CSS Variables (.css file download)
- Export as Tailwind Config (.js file download)
- Filter by project dropdown

## Data & Persistence

- All assets stored in localStorage as JSON array under `assetvault_assets`
- Projects derived dynamically from asset `project` fields
- Theme preference stored under `assetvault_theme`
- 6 seed assets auto-populated on first load across 2 demo projects

## Key Interactions

- Real-time search (debounced 200ms) across name, tags, project
- Sidebar filtering by type or project
- Grid (3-4 col responsive) and List view toggle
- Toast notifications for all CRUD and export actions
- Delete confirmation modal
- Empty states with friendly messaging and CTA
- Mobile responsive: sidebar collapses to hamburger drawer

