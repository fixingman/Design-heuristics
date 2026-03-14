# Skill: Design QA

Load when: accessibility review, WCAG compliance check, heuristic evaluation, anti-pattern audit, pre-release design review, or Figma implementation check.

---

## ACCESSIBILITY (WCAG 2.2)

**POUR:** Perceivable / Operable / Understandable / Robust

**Contrast:**
- Normal text (<18px): 4.5:1 (AA) → 7:1 (AAA)
- Large text: 3:1 (AA)
- UI components, icons: 3:1

**Color is NEVER the only indicator:** Error = red + ⚠ icon + text. Status = color + symbol + label. Charts = colors + patterns + labels.

**Touch targets:** WCAG 2.2 AA minimum 24×24px. Recommended 44×44px. Ideal 48×48dp.

**Focus:** Visible 2px accent ring with 2px offset. Focus trap in modals. Tab order follows visual order top→bottom, left→right.

**Text:** Min body 16px (prevents iOS zoom), min caption 12px. NEVER weight 100/200/300 at <18px.

**Color blindness (8% of men):** Red+green must have additional differentiator. Test with Color Blind Figma plugin.

**Motion:** Respect `prefers-reduced-motion`. Replace slides/scales with fades or cuts. Keep essential feedback. NEVER flash >3×/second.

**Forms:** Every input has associated visible label. Required fields: asterisk + aria-required. Errors announced by screen reader (aria-live). Correct autocomplete attributes.

---

## NIELSEN'S 10 HEURISTICS

1. **Visibility of system status** — Loading indicators, progress, active states. Never silent.
2. **Match with real world** — User language, not system jargon. Familiar metaphors. Human error messages.
3. **User control & freedom** — Back/close on every screen. Undo for destructive actions. Cancel mid-flow.
4. **Consistency & standards** — Same action = same visual everywhere. One CTA color. Consistent terminology.
5. **Error prevention** — Masks for formatted fields. Confirmation before destructive. Smart defaults. Inline validation.
6. **Recognition over recall** — Visible labels. Icons with text labels. Recent history. Help without leaving screen.
7. **Flexibility & efficiency** — Shortcuts for frequent actions. Gestures. Quick actions. Repeat last action.
8. **Aesthetic & minimalist design** — Every element has purpose. Max 3-4 info blocks/screen. Breathing room.
9. **Help recover from errors** — WHAT happened + WHY + WHAT to do. Recovery action button. Near the field.
10. **Help & documentation** — Tooltips for complex fields. Contextual help. Onboarding for new features.

**Severity:** 0=not an issue / 1=cosmetic / 2=minor / 3=major (fix before launch) / 4=catastrophic (fix immediately)

---

## ANTI-PATTERNS — NEVER DO THESE

| # | Anti-Pattern | Fix |
|---|---|---|
| AP-01 | Oval/cylindrical button | FIXED width = FIXED height, cornerRadius = size/2 |
| AP-02 | Color soup (different color per button) | 1 accent for ALL primary. Hierarchy by style only |
| AP-03 | Inconsistent card padding | Choose 1 padding value for all cards of same type |
| AP-04 | Mixed border-radius | Max 2 values + pill. Choose and stick to it |
| AP-05 | Illegible text (#CCC on white, 10px, Light weight) | Min 16px body, 4.5:1 contrast, weight 400+ |
| AP-06 | Two filled primary CTAs | Only 1 filled. Others outlined or ghost |
| AP-07 | Primary CTA at top on mobile | CTA always in bottom half (thumb zone) |
| AP-08 | Generic labels ("OK", "Yes", "Submit") | Verb + noun: "Send Payment", "Delete Account" |
| AP-09 | No loading feedback (screen freezes) | Visual feedback <100ms. Loading if >400ms |
| AP-10 | Modal without exit | X + Cancel + overlay tap + swipe down |
| AP-11 | Elements floating loose on Figma canvas | Everything inside Section → Frame hierarchy |
| AP-12 | FILL before appendChild in auto-layout | Append child first, THEN set FILL |
| AP-13 | Same color for bg + card + button | Distinct elevation layers in dark mode |
| AP-14 | Bottom nav icons without labels | Icon + label always |
| AP-15 | Excessive animation | 300ms transitions, micro-interactions only where needed |
| AP-16 | No typographic hierarchy | Min 3 different sizes with clear weight contrast |
| AP-17 | Card with too much information | Max 3-4 lines, key info only, "View →" for rest |

---

## SELF-REVIEW CHECKLIST

### Visual:
- [ ] Only 1 primary CTA (filled)?
- [ ] Circular buttons ACTUALLY circular (width=height, cornerRadius=size/2)?
- [ ] Only 1 accent color on screen?
- [ ] Consistent border-radius on all elements of same type?
- [ ] Uniform padding on cards/containers?
- [ ] Clear typographic hierarchy (≥3 different sizes/weights)?
- [ ] Text contrast ≥4.5:1?

### Functional:
- [ ] CTA in thumb zone (bottom half)?
- [ ] Button labels descriptive (verb + noun)?
- [ ] All components have press feedback?
- [ ] Loading states for actions >400ms?
- [ ] Modals have ≥2 ways to close?
- [ ] Back button on all sub-screens?
- [ ] No action uses color as only indicator?

### Figma Technical:
- [ ] Everything in auto-layout?
- [ ] No elements floating on canvas?
- [ ] FILL applied AFTER appendChild?
- [ ] Fonts loaded before use (loadFontAsync)?
- [ ] Colors in normalized RGB (0-1), not hex?
- [ ] Reactions use `actions` (plural) and `setReactionsAsync`?
- [ ] Durations in reactions in SECONDS (0.35), not ms?
- [ ] `getNodeByIdAsync` not `getNodeById`?
- [ ] `overflowDirection` uses 'HORIZONTAL' not 'HORIZONTAL_SCROLLING'?
- [ ] Layers named with prefix convention (Screen/, Section/, Card/, etc.)?
