# Skill: Design Interaction & Motion

Load when: questions about animations, transitions, motion timing, micro-interactions, or haptics.

---

## MOTION & TRANSITIONS (M3 System)

**Default:** GENTLE easing at 350ms for ALL transitions unless specified otherwise.

**M3 Easing → Figma:**
- Emphasized → GENTLE (screen transitions, important moves)
- Emphasized Decelerate → EASE_OUT (elements entering)
- Emphasized Accelerate → EASE_IN (elements exiting)
- Standard → EASE_IN_AND_OUT (utility, tabs, toggles)
- Linear → LINEAR (spinners, skeleton shimmer)

**Duration tokens:**
- 50-100ms: Press feedback, hover states
- 150-200ms: Tooltips, toggles, checkboxes
- 250-300ms: Tab switches, small expansions
- 350ms ⭐: Screen transitions (default)
- 400-500ms: Complex transitions, modals
- 500-700ms: Success screens, celebrations
- Exit is always ~50ms faster than enter

**Transition patterns:**
| Pattern | Figma | Use |
|---|---|---|
| Container Transform | SMART_ANIMATE | Card → detail page |
| Shared X-Axis forward | SLIDE_IN LEFT | CTA → next screen |
| Shared X-Axis back | SLIDE_IN RIGHT | Back button |
| Shared Y-Axis | SLIDE_IN BOTTOM | Modal / bottom sheet |
| Fade Through | DISSOLVE | Tab switches |
| Fade | DISSOLVE as OVERLAY | Tooltips, dialogs |

**Motion anti-patterns:** >700ms for routine transitions. Bounce in financial/medical apps. Inconsistent directions. Loading animation blocking interaction. Animation without communicative purpose.

---

## MICRO-INTERACTIONS (Dan Saffer Framework)

Every micro-interaction: Trigger → Rules → Feedback → Loops

**Key catalog:**
- Toggle: Knob slides 150-200ms, track changes color, haptic light
- Like: Scale 1.0→1.3→1.0, outline→filled, 300-400ms
- Button press: Scale 1.0→0.97, opacity 0.9 on touch-down. SIZE NEVER CHANGES
- Input focus: Border neutral→2px accent 150ms, label animates up, keyboard rises
- Skeleton→content: Fade out skeleton 150ms, staggered fade-in content 200ms +30-50ms each

**"Delightful but dismissible" principle:** If the user does this 50×/day and it would irritate → remove it. Pleasant the 1st time, invisible the 100th.

**When NOT to use:** On everything (fatigue). On very frequent scroll. In final checkout steps. Bounces in financial/medical apps.
