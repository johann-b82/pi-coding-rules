---
name: ui-ux-pro-max
description: Detailed UI/UX design rules, WCAG AA accessibility checklists, styling systems, visual feedback times, and performance strategies for professional interfaces.
---

# UI/UX Pro Max Design Guidelines

Use this skill when designing, reviewing, or styling any frontend UI, layouts, or component states.

## 1. Absolute Accessibility (WCAG AA)
* **Contrast Richness:** Text-to-background contrast ratio must be $\ge 4.5:1$ (AA) for normal body text, and $\ge 3:1$ for headers. Never use low-contrast grays on gray background.
* **Semantic Aria Structure:** Always append descriptive `aria-label` / `accessibilityLabel` attributes on icon-only buttons or interactive indicators.
* **Keyboard Navigation:** Preserve system focus rings (never disable focus states) and ensure the tab sequence matches visual hierarchy.
* **System Settings Compatibility:** Honor system text scaling and respect `prefers-reduced-motion` settings.

## 2. Touch & Click Ergonomics
* **Comfortable Targets:** Any touch targets (buttons, links, drawer nodes) must be $\ge 44 \times 44 \text{ px}$ with $\ge 8\text{px}$ gaps to prevent accidental taps.
* **Interactive Cursors:** Always declare `cursor-pointer` explicitly on clickable elements.
* **Feedback States:** Active press, hover, focus, disabled, and loading states must react instantly ($150\text{–}300\text{ms}$ smooth transitions).

## 3. High Performance & Layout Shifts (CLS)
* **Zero Content Jumps:** Always set explicit `width`/`height` dimensions or `aspect-ratio` on images and media containers to keep Cumulative Layout Shift $< 0.1$.
* **Progressive Loading:** Map heavy elements or media below-the-fold for lazy-loading. Use clean skeleton screens or shimmer layouts for asynchronous data streams.

## 4. Architectural Styling & Consistency
* **No Emojis as Icons:** Always use high-quality vector SVGs (e.g., Lucide, Heroicons, or native framework design assets).
* **Navigation Densities:** Limit top/bottom mobile navigation menus to $\le 5$ primary links. Keep navigation positions consistent across page templates.
