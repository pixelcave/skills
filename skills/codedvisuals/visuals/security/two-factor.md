---
name: codedvisuals-security-two-factor
description: A one-time code typed into two input groups, with the lock turning into a check as a pulse ripples through concentric rings. The Two-Factor visual in the Security category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Security / Two-Factor

A one-time code typed into two input groups, with the lock turning into a check as a pulse ripples through concentric rings.

- **Registry name:** `@codedvisuals/security-two-factor`
- **Import path:** `@/components/codedvisuals/security/two-factor`

## Install if it is not in the project yet

Look for `components/codedvisuals/security/two-factor.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/security-two-factor
```

This uses the private registry (one time setup) and installs Motion and lucide-react if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`), the presentation modifier (`isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `code` | `string` | `"482915"` |
| `pulse` | `boolean` | `true` |

## Examples

Give the visual a sized container, then drop it in:

```tsx
import SecurityTwoFactor from "@/components/codedvisuals/security/two-factor";

// default
<SecurityTwoFactor />

// isometric
<SecurityTwoFactor isometric />

// custom copy
<SecurityTwoFactor code="730164" />

// code="5821"
<SecurityTwoFactor code="5821" />

// code="90417352"
<SecurityTwoFactor code="90417352" />

// pulse={false}
<SecurityTwoFactor pulse={false} />
```
