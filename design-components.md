# Skill: Design Components

Load when: questions about buttons, forms, inputs, navigation, cards, lists, feedback states, or loading patterns.

---

## BUTTONS & CTAs

**Hierarchy (mandatory):**
- Primary: Filled solid accent — MAX 1 PER SCREEN
- Secondary: Outlined accent — max 2
- Tertiary: Ghost/text — as many as needed

**Sizes:** XSmall 32px / Small 36px / Medium 44px / Large 48-56px

**Circular buttons:** width === height. cornerRadius = size/2. FIXED sizing on BOTH axes. NEVER HUG on circular button.

**States:** Default / Hover / Pressed (scale 0.97-0.98) / Focused (2px accent ring) / Disabled (40% opacity, same size) / Loading (spinner replaces text, size unchanged)

**Labels:** Verb + noun. "Send Payment" not "OK". "Delete Account" not "Yes". Max 3-4 words.

**Positioning:** Primary CTA in bottom half (thumb zone). Cancel (ghost) left, Confirm (filled) right in modals.

**Icons in buttons:** Left = reinforces meaning. Right = direction/progression. Icon-only = only for universally recognized actions.

---

## FORMS & INPUTS

**Anatomy:** Label (14px SemiBold, above field) → Input (48px height, 16px font min) → Helper text (12px)

**Spacing:** Label→Input: 4-8px. Input→Helper: 4px. Field→Field: 16-20px. Group→Group: 32px

**States:** Default (1px neutral border) / Hover (darker border) / Focused (2px accent border + accent label) / Error (2px red border + ⚠ icon + error message) / Disabled (neutral-100 bg, neutral-400)

**Rules:**
- Label ALWAYS visible above field (never placeholder-only)
- Placeholder = format example, NOT a label substitute
- Input font ≥ 16px (prevents iOS auto-zoom)
- Choose 1 height for entire form — NEVER mix
- Validate onBlur (not onChange) except passwords and search
- Error: red + ⚠ icon + descriptive text (never color-only)

**Special inputs:**
- PIN/OTP: Individual fields, 48×56px each, 8-12px gap, auto-focus to next
- Password: 👁 toggle on right, strength indicator bar
- Search: 🔍 leading, X clear button on right

---

## NAVIGATION

**Bottom nav:** 3-5 items (never more). Height 56-83px. Icon 24px + label 10-12px. Active: filled icon + accent. Min touch target 48×48px per item.

Standard layout: Home (1) | Search (2) | Main action (3) | Activity (4) | Profile (5)

**Top header:** Height 44-56px. ← back top-left with 44×44px target. Max 2 action icons right.

**Tabs:** Below header, sticky. 2px accent indicator. Swipeable content.

**Drawer:** 80% width max 320px. 50-60% overlay. Open: swipe left edge or ☰.

**Gestures:** Swipe right = back (iOS stack). Swipe down = close modal. Swipe left on item = delete. Pull down = refresh. ALL gestures need button alternative.

**Navigation transitions:** Push forward: SLIDE_IN LEFT 350ms GENTLE. Pop back: SLIDE_IN RIGHT 350ms GENTLE. Modal open: SLIDE_IN BOTTOM 350ms GENTLE. Tab switch: DISSOLVE 250ms GENTLE.

---

## CARDS & LISTS

**Card rules:**
- All cards in same list: same border-radius (12-16px), same padding (16-24px), same shadow
- Gap between cards: 12-16px
- Press feedback: scale 0.98 + opacity 0.9
- Max 3-4 lines of text per card. Max 2 actions per card.
- NEVER: different padding/radius on cards of the same type

**List item:** Height 56px (1 line) / 72px (2 lines). Horizontal padding 16px. Leading: avatar 40-48px / icon 24px. Divider: 1px inset (aligned with text, not full-width).

**Empty states:** Centered illustration (120-160px) + descriptive title + subtitle with action suggestion + optional secondary CTA.

**Skeleton loading:** Shape mirrors real content. Color neutral-200 + shimmer. Shimmer left→right, 1.5-2s loop. ALWAYS prefer skeleton over spinner for page loading.

---

## FEEDBACK & STATES

**Fundamental rule:** Every action receives visual response in <100ms. Loading if >400ms. Never silent.

| Action duration | Feedback |
|---|---|
| <300ms | Immediate visual change only |
| 300ms-2s | Inline spinner in button |
| 2-10s | Progress bar + descriptive text |
| >10s | Progress bar + time estimate + "notify when ready" |

**Toasts/Snackbars:** Bottom (above bottom nav), 16px margin. 48-56px height. Auto-dismiss 3-5s. Max 1 action ("Undo"). Max ~60 chars. Types: ✓ success (green) / ✕ error (red) / ⚠ warning (yellow) / ℹ info (neutral).

**Confirmation modals:** Use for destructive/irreversible actions. Title = clear question. Description = consequence. Cancel ghost left, Destructive red right. Overlay 50-60%. NEVER "Yes"/"No" labels.

**Success screens:** Animated check (scale 0→1.2→1.0, 400-600ms). Show essentials (amount, recipient). Post-success CTAs. Invest design here — user remembers endings.

**Error screens:** Illustration + plain language (WHAT happened + WHY + WHAT to do) + recovery CTA.

**Loading patterns:** Spinner for buttons/inline. Skeleton for content pages. Progress bar for uploads/known progress (4-8px height, pill border-radius).
