# 840e5c98-1b20-4b51-89d6-8b9dcab9ae73 implementation handoff

This archive is the source of truth for turning the design into production code. Start from `index.html`, then preserve the visual system, responsive behavior, and interactions found in the exported files.

## Implementation target
- Build production UI from the exported design, not a loose reinterpretation.
- Preserve typography scale, spacing rhythm, color tokens, border radii, shadows, motion timing, and component states.
- Replace static placeholders only when the target app has real data or functional equivalents.
- Keep generated product UI free of Open Design chrome, preview labels, or design-process annotations.
- Treat this handoff as a visual contract: if implementation choices conflict, match the exported pixels and behavior first, then refactor internals.

## Source map
- Primary entry: `index.html`
- HTML screens detected: 1
- Stylesheets detected: 1
- Script/component files detected: 0
- Supporting assets detected: 28

## Responsive contract
Validate the implementation across this 2025–2026 viewport matrix:
- Mobile compact: 360×800
- Mobile standard: 390×844
- Mobile large: 430×932
- Foldable / small tablet: 600×960
- Tablet portrait: 820×1180
- Tablet landscape: 1024×768
- Laptop: 1366×768
- Desktop: 1440×900
- Wide desktop: 1920×1080

For responsive web exports, treat these as a modern breakpoint system for one adaptive web experience, not three fixed screenshots. Do not split responsive web into unrelated native app screens unless the project explicitly includes native targets. Use semantic layout thresholds, fluid `clamp()` type/spacing, and container queries where component width matters more than viewport width. Preserve any CSS media queries, container queries, fluid `clamp()` scales, and layout changes already present in the exported files.

## Design fidelity contract
- Extract reusable tokens before writing components: background, surface, foreground, muted text, border, accent, radius, shadow, spacing, type scale, and motion duration/easing.
- Map product screens, in-app modules/components, optional landing page, and optional OS widget surfaces before coding. Keep these surfaces separate in the target architecture.
- Match layout geometry: max-widths, gutters, grid columns, card proportions, sticky/fixed elements, and viewport-specific navigation.
- Preserve real copy, labels, and data shown in the export. Do not replace specific text with generic marketing filler.
- Preserve interactive affordances: hover, focus, pressed, disabled, loading, validation, copy/share, tab/accordion, modal/sheet, and keyboard states where present.
- Preserve accessibility semantics when converting: headings stay hierarchical, controls remain buttons/links/inputs, focus states stay visible.
- Do not keep prototype-only annotations, frame labels, or Open Design chrome in the production UI.

## CJX-ready UX contract
- Use `DESIGN-MANIFEST.json` as the machine-readable map for screens, app modules, OS widgets, landing pages, tokens, interactions, and viewport checks.
- Screen-file-first: when multiple user-facing surfaces exist, implement each HTML screen as its own route/file. Treat `index.html` as a launcher/overview when the manifest marks it that way, not as a combined final UI.
- If `landing.html`, app screens, platform screens, or OS widget files exist, preserve those boundaries in the target app instead of merging them into one page.
- A single self-contained `index.html` is acceptable only when the export truly contains one user-facing screen and its CSS/JS are structured enough to extract tokens, components, states, and behavior.
- If separate `css/` or `js/` files exist, treat them as source of truth for token/component/interactions before porting to React, Vue, SwiftUI, Compose, or another target stack.
- In-app modules/components are product UI blocks inside the app. OS widgets are home-screen/lock-screen/quick-access surfaces outside the app. Do not merge those concepts.

## Color and brand contract
- Use the exported design tokens and product/domain context as the color source of truth.
- Do not introduce warm beige / cream / peach / pink / orange-brown background washes unless they are already explicit brand/reference colors in the export.
- A stylesheet or design/token file was detected; inspect it for canonical color variables before choosing framework theme tokens.

## Implementation sequence for AI coding tools
1. Open `index.html` and `DESIGN-MANIFEST.json`; identify every screen file, launcher/overview file, app module, and interaction before coding.
2. If multiple HTML screens exist, map them to separate routes/surfaces first; do not merge `landing.html`, product app screens, platform screens, or OS widgets into one route.
3. Extract a token table from CSS/root styles and inline styles before building framework components.
4. Build product screens and domain-specific in-app modules from largest layout regions down to controls; avoid starting with isolated atoms that lose spatial intent.
5. Port responsive behavior across the modern viewport matrix and test each semantic breakpoint before cleanup.
6. Port interactions and states, then replace static placeholders only with real app data or functional equivalents.
7. Keep optional landing page and OS widget surfaces as separate surfaces if present.
8. Compare final screenshots against the export at 360×800, 390×844, 430×932, 820×1180, 1024×768, 1366×768, 1440×900, and 1920×1080 before declaring done.

## Entry points
- `index.html`

## Styles
- `style.css`

## Scripts/components
- None detected

## Assets and supporting files
- `mqk0g4v4-517657818_18288355237251635_8592416156784706897_n.jpg`
- `mqk0g4w0-719032352_17967625449078031_3050598658717163859_n.jpg`
- `mqk0g4yt-ChatGPT-Image-Jun-18_-2026_-03_44_54-PM.png`
- `mqk0g51e-ChatGPT-Image-Jun-18_-2026_-03_44_59-PM.png`
- `mqk0g54j-ChatGPT-Image-Jun-18_-2026_-03_45_04-PM.png`
- `mqk0g58i-ChatGPT-Image-Jun-18_-2026_-03_45_09-PM.png`
- `mqk0g5ey-ChatGPT-Image-Jun-18_-2026_-03_45_13-PM.png`
- `mqk0g5ik-ChatGPT-Image-Jun-18_-2026_-03_45_18-PM.png`
- `mqk0g5ma-ChatGPT-Image-Jun-18_-2026_-03_45_22-PM.png`
- `mqk0g5tm-ChatGPT-Image-Jun-18_-2026_-03_45_26-PM.png`
- `mqk0g5x5-ChatGPT-Image-Jun-18_-2026_-03_45_33-PM.png`
- `mqk0g60o-ChatGPT-Image-Jun-18_-2026_-03_45_45-PM.png`
- `mqk0g64r-ChatGPT-Image-Jun-18_-2026_-03_45_58-PM.png`
- `mqk0g67e-ChatGPT-Image-Jun-18_-2026_-03_46_02-PM.png`
- `mqk0g6a4-imgi_5_20210103_TWD_1729_1080x1080.jpg`
- `mqk0g6b0-imgi_6_20210103_TWD_1659_1080x1080.jpg`
- `mqk0g6b8-imgi_8_20210103_TWD_0072_1080x1080.jpg`
- `mqk0g6c1-imgi_9_20210103_TWD_2139_1080x1080.jpg`
- `mqk0g6cx-imgi_10_20210103_TWD_0382_1080x1080.jpg`
- `mqk0g6dv-imgi_11_20210103_TWD_3040_1080x1080.jpg`
- `mqk0g6ed-imgi_12_20210103_TWD_0766_1080x1080.jpg`
- `mqk0g6f7-imgi_22_716550765_18330854569251635_4325386102604952805_n.jpg`
- `mqk0g6fz-imgi_27_ttwd-site-00011_300x.jpg`
- `mqk0g6fz-imgi_39_20210103_TWD_2610.jpg`
- `mqk0g6ix-imgi_40_20210103_TWD_1573.jpg`
- `mqk0g6ku-TWD_lOGO_White.webp`
- `mqk0g6ld-516815495_18288355201251635_3282432673302785420_n.jpg`
- `mqk0lhs3-The-Things-We-Do-Beauty---Sales-Page-Copy---2026-06-07T12_51_38.661_06_00.txt`

## Coding checklist for AI tools
1. Inspect `index.html` and `DESIGN-MANIFEST.json` first and identify reusable components before coding.
2. Implement each user-facing screen file as its own route/surface; keep launcher, landing, app, platform, and OS widget files separate.
3. Extract design tokens into the target stack: colors, type scale, spacing, radius, shadows, and motion.
4. Implement layout with real 2025–2026 responsive breakpoints, fluid type/spacing, and container-query-aware component behavior; test with no horizontal overflow.
5. Preserve interactive controls, hover/focus/pressed states, form behavior, validation, and copy actions where present.
6. Implement domain-specific in-app modules with real states; do not flatten them into generic cards.
7. Keep landing page, product screens, and OS widget/quick-access surfaces separate when present.
8. Confirm the production result visually matches the exported design before refactoring internals.
9. Reject implementation shortcuts that flatten the design into generic cards, generic gradients, placeholder stats, or framework-default typography.
10. If a detail is ambiguous, keep the exported HTML/CSS/JS behavior rather than inventing a new pattern.
