# Skill: Design Foundations

Load when: discussing core design principles, UX laws, Gestalt, or doing a general design review from scratch.

---

## CORE PRINCIPLES

### Before creating any screen:
1. Define visual hierarchy — what does the user see FIRST? SECOND? THIRD?
2. One primary action per screen — never compete with 2 CTAs of equal weight
3. White space is not waste — it's clarity
4. Consistency over creativity — if the design system defines a pattern, follow it
5. Mobile-first — start from the smallest viewport and expand

### The 4 Pillars:
- **Hierarchy**: Size, weight, color, position, spacing
- **Contrast**: Min 4.5:1 for normal text (WCAG AA); 3:1 for large text (≥18px bold or ≥24px)
- **Alignment**: Everything aligns to something. Use 8px grid for all spacing
- **Proximity**: Related 8-12px apart, unrelated 24-32px+. Space between groups ≥ 2× space within groups

### Mobile Golden Rules:
- Touch targets: min 44×44px (Apple HIG) / 48×48dp (Material). Gap between targets: min 8px
- Circular buttons: width === height, cornerRadius = width/2. NEVER oval
- Safe areas: top 44px iOS / 24dp Android, bottom home indicator 34px iOS
- Primary actions in the bottom half (thumb zone)
- Min text: body 16px, caption 12px, screen title 20-28px

---

## UX LAWS

| Law | Rule |
|---|---|
| **Fitts's** | Larger + closer = faster. Primary CTA full-width on mobile. Destructive actions smaller and far from main CTA |
| **Hick's** | Max 5 bottom nav items, max 5-7 form fields visible, 1 primary + max 2 secondary actions per screen |
| **Jakob's** | Use familiar patterns. Back top-left. Pull to refresh. Swipe left to delete. Search = magnifying glass |
| **Miller's** | Group data in chunks ≤7. Phone/card numbers in groups. OTP = individual fields |
| **Von Restorff** | Primary CTA = ONLY element with accent color on screen. Others outlined or ghost |
| **Serial Position** | Most important at first or last position. Middle is forgotten |
| **Doherty** | Visual feedback <100ms. Loading state if >400ms. Screen transition 200-500ms |
| **Aesthetic-Usability** | Beautiful = perceived as easier. Generous spacing, consistent border-radius, max 3 colors + neutrals |
| **Peak-End** | Invest in success screens — user remembers first + last moment. Animate the confirmation |
| **Zeigarnik** | Show progress. "Step 2 of 4". Profile completion %. Never hide progress in multi-step flows |
| **Tesler's** | System absorbs complexity. Autocomplete, smart defaults, auto-formatting. Never make user type what system can infer |
| **Postel's** | Accept flexible input formats (phone with/without dashes), display in correct format |

---

## GESTALT PRINCIPLES

| Principle | Rule |
|---|---|
| **Proximity** | Within group: 8-12px. Between groups: 24-32px. Label→Input: 4-8px. Sections: 32-48px |
| **Similarity** | All primary buttons: same color, border-radius, weight. All cards: same radius, shadow, padding |
| **Continuity** | Consistent left margin. Carousel: clip last item at ~30% to invite scroll |
| **Closure** | Cards don't need borders — background + padding creates container perception |
| **Figure-Ground** | Modal: 50-60% overlay. Dropdown: level 2 shadow. FAB: pronounced shadow |
| **Common Region** | Related info inside same card/container. Never mix unrelated content in one card |
| **Symmetry** | Consistent padding (if left=24px, right=24px). Equal distribution in bottom nav |
| **Common Fate** | Elements in same group animate together. Skeleton shimmer moves in same direction |

**Elevation shadows:**
- Level 1 (cards/inputs): `0 1px 3px rgba(0,0,0,0.08)`
- Level 2 (dropdowns): `0 4px 12px rgba(0,0,0,0.12)`
- Level 3 (modals/bottom sheets): `0 8px 24px rgba(0,0,0,0.16)`
- Level 4 (FAB): `0 12px 32px rgba(0,0,0,0.20)`
