# Skill: Design Visual System

Load when: questions about spacing, layout grid, typography tokens, color choices, dark mode, or contrast.

---

## LAYOUT & SPACING (8px Grid)

**Spacing scale:** 2 / 4 / 8 / 12 / 16 / 24 / 32 / 40 / 48 / 64px

**Screen margins:** Mobile: 16-24px sides. Tablet: 24-32px, max-width 600px. Desktop: max-width 1200px

**Default viewport:** 393×852px (iPhone 15 Pro)

**Auto-layout rules:**
- EVERYTHING uses auto-layout — no manually positioned elements except overlays
- Set FILL on child ONLY AFTER appending child to auto-layout parent
- Full-width button: layoutSizingHorizontal = FILL, height FIXED 48-56px

**Safe areas:**
- iOS: status bar 47px (Dynamic Island) / 44px (notch); home indicator 34px bottom
- NEVER place interactive elements in safe areas

---

## TYPOGRAPHY

| Token | Size | Weight | Line Height | Use |
|---|---|---|---|---|
| display-xl | 40px | 700 | 48px | Hero |
| heading-xl | 28px | 600 | 36px | Screen title |
| heading-lg | 24px | 600 | 32px | Section title |
| heading-md | 20px | 600 | 28px | Card title |
| body-lg | 16px | 400 | 24px | Body, inputs |
| body-md | 14px | 400 | 20px | Labels |
| body-sm | 12px | 400 | 16px | Caption, helper |

**Rules:**
- Max 2 font families (1 sans-serif + 1 mono if needed)
- Max 3 weights. Regular + SemiBold = minimum. NEVER Light/Thin on mobile
- Line height = font-size × 1.3-1.5, rounded to multiple of 4
- Sentence case everywhere. UPPERCASE only for overlines (≤3 words)
- Body minimum 16px. Caption minimum 12px. NEVER smaller
- Recommended: Inter, SF Pro (iOS), Roboto (Android), DM Sans, Plus Jakarta Sans
- Large values: use tabular numbers (tnum or monospace)

---

## COLOR SYSTEM

**Required semantic tokens:**
| Token | Light | Dark | Use |
|---|---|---|---|
| accent | #276EF1 | #5B8DEF | CTAs, links, focus |
| positive | #0E8345 | #34C759 | Success |
| warning | #F6BC2F | #FFD60A | Alerts |
| negative | #DE1135 | #FF453A | Errors, delete |

**Neutral palette (light):** #1A1A1A (headings) → #333 (body) → #666 (secondary) → #999 (placeholder) → #CCC (borders) → #E5E5E5 (subtle borders) → #F0F0F0 (card bg) → #FFF (background)

**Dark mode:**
- NEVER #FFFFFF text — use #E0E0E0
- NEVER #000000 background — use #121212
- Elevation = lighter backgrounds: #121212 → #1E1E1E → #252525 → #2C2C2C

**Contrast (WCAG 2.2 AA):**
- Normal text (<18px): 4.5:1 minimum
- Large text (≥18px bold or ≥24px): 3:1 minimum
- FORBIDDEN: #CCC on #FFF (1.6:1), yellow on white (1.07:1)

**Opacity for states:** Hover: 90% / Pressed: 80% / Focused: 100% + 2px ring / Disabled: 40% / Selected bg: accent 8-12%

**Max per screen:** 1 accent + 1 background + 1-2 neutrals + status colors when needed
