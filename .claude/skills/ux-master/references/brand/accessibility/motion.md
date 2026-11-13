# Motion accessibility — Merkle Accessibility Advocate

Motion and animation must respect `prefers-reduced-motion`. This is both a WCAG 2.1 requirement (SC 2.3.3, AAA; SC 2.3.1, A for triggerable/looping content) and a practical responsibility: vestibular disorders, motion sickness, and cognitive difficulties make animation harmful for a meaningful portion of users.

MDS uses `motion/react` (Framer Motion). Every `motion.*` component, `AnimatePresence`, and CSS transition on a Merkle surface must behave correctly when the OS preference is set to reduce motion.

---

## The rule

When `prefers-reduced-motion: reduce` is active, all MDS animation must either:
1. **Produce no spatial movement** — position, scale, rotation, and blur transitions stop entirely, or
2. **Fall back to an opacity-only fade** — a short opacity transition (100–150ms) is acceptable because it does not involve spatial displacement

Opacity transitions are generally safe to keep. The following must be suppressed: translate (x, y), scale, rotation, blur/filter.

---

## Detecting the preference in React

``tsx
import { useReducedMotion } from "motion/react";

function MyPanel({ children }: { children: React.ReactNode }) {
  const shouldReduceMotion = useReducedMotion();

  const variants = shouldReduceMotion
    ? {
        hidden: { opacity: 0 },
        visible: { opacity: 1 },
        exit: { opacity: 0 },
      }
    : {
        hidden: { opacity: 0, y: 48 },
        visible: { opacity: 1, y: 0 },
        exit: { opacity: 0, y: 24 },
      };

  return (
    <motion.div
      initial="hidden"
      animate="visible"
      exit="exit"
      variants={variants}
      transition={
        shouldReduceMotion
          ? { duration: 0.15, ease: "easeOut" }
          : SPRING
      }
    >
      {children}
    </motion.div>
  );
}
``

`useReducedMotion()` returns `true` when the OS preference is active:
- macOS: System Preferences → Accessibility → Display → Reduce Motion
- iOS: Settings → Accessibility → Motion → Reduce Motion
- Windows: Settings → Ease of Access → Display → Show animations

---

## MDS motion constants

Do not change `bounce` values or `duration` values on these constants.

``ts
const SPRING      = { type: "spring", duration: 0.35, bounce: 0 } as const;
const SPRING_FAST = { type: "spring", duration: 0.25, bounce: 0 } as const;
``

When `prefers-reduced-motion: reduce` is active, replace the SPRING transition with a flat ease — do not apply SPRING to a movement-free opacity fade, as the spring physics will still produce a very brief but non-zero movement.

---

## AnimatePresence conventions

All MDS `AnimatePresence` usage sets `initial={false}`:

``tsx
// Correct
<AnimatePresence initial={false}>
  {isVisible && (
    <motion.div key="panel" variants={variants} initial="hidden" animate="visible" exit="exit">
      {content}
    </motion.div>
  )}
</AnimatePresence>

// Wrong — initial={true} animates on first render before the user has interacted
<AnimatePresence>
``

`initial={false}` prevents the entry animation from firing on the component's first mount — it only animates when the presence actually changes after the parent is already rendered.

Under reduced-motion, the presence change still happens; the component should fade rather than disappear instantly. Provide an opacity variant so there is a brief crossfade.

---

## Standard MDS animation patterns with reduced-motion equivalents

| Interaction | Full motion | Reduced motion |
|---|---|---|
| Panel/drawer enter | `y: 48 → 0`, `opacity: 0 → 1`, SPRING | `opacity: 0 → 1`, 150ms ease-out |
| Panel/drawer exit | `y: 0 → 24`, `opacity: 1 → 0`, SPRING | `opacity: 1 → 0`, 100ms ease-in |
| Icon entrance | `scale: 0.5 → 1`, `opacity: 0 → 1`, `blur(4px) → 0`, SPRING_FAST | `opacity: 0 → 1`, 100ms ease-out |
| Scale on press | `scale: 0.96` on pointer-down | Remove scale — no spatial feedback |

Scale-on-press (`scale: 0.96`) is the MDS convention for interactive element press feedback. Under reduced-motion, suppress the scale entirely — the default `:active` state provides sufficient feedback without movement.

---

## CSS transitions

`motion/react` handles most MDS animation, but CSS transitions are used for hover and state changes on token-driven surfaces (button colour, border, focus ring).

``css
/* Wrap spatial transitions in the media query */
.my-element {
  transition:
    background-color 150ms ease,
    transform 200ms ease;
}

@media (prefers-reduced-motion: reduce) {
  .my-element {
    /* Keep colour; drop transform */
    transition: background-color 150ms ease;
  }
}
``

For MDS component CSS files, follow the same pattern — declare both sets. Do not use `transition: none` globally; it removes colour transitions that are safe and expected.

---

## What to keep vs suppress

| Animation type | Under prefers-reduced-motion |
|---|---|
| Opacity fade (100–150ms) | ✅ Keep — no spatial displacement |
| Colour / background transitions | ✅ Keep |
| Border / outline transitions | ✅ Keep |
| Position (x, y, translate) | Remove |
| Scale | Remove |
| Rotation | Remove |
| Blur / filter | Remove |
| Parallax / scroll-linked position | Remove |
| Auto-playing video or GIF | Pause or provide a pause control (WCAG 2.2.2) |

---

## Testing

**Enable in browser:** Chrome DevTools → Rendering panel → Emulate CSS media feature → `prefers-reduced-motion: reduce`

**Enable in OS:**
- macOS: System Preferences → Accessibility → Display → Reduce Motion
- Windows: Settings → Ease of Access → Display → Show animations in Windows (off)

**Verify after enabling:**
- Panels and drawers appear without spatial movement
- Buttons do not scale on press
- Icons appear without scale/blur entrance effects
- Any scroll-driven parallax stops
- The UI remains fully functional — layout must not break when animations are stripped
