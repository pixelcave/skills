---
name: codedvisuals-hero-security-gateway
description: A wide isometric hero scene where request lanes run into a firewall wall, clean traffic passing through open gates to your app while blocked lanes stop at red gates. The Security Gateway visual in the Hero category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Hero / Security Gateway

A wide isometric hero scene where request lanes run into a firewall wall, clean traffic passing through open gates to your app while blocked lanes stop at red gates.

- **Registry name:** `@codedvisuals/hero-security-gateway`
- **Import path:** `@/components/codedvisuals/hero/security-gateway`

## Install if it is not in the project yet

Look for `components/codedvisuals/hero/security-gateway.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/hero-security-gateway
```

This uses the private registry (one time setup) and installs Motion, lucide-react, and cn if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `logo` | `React.ReactNode \| null` | see Default content below |
| `requests` | `GatewayRequest[]` | see Default content below |
| `app` | `GatewayTarget` | see Default content below |
| `allowedLabel` | `string` | `"Allowed"` |
| `blockedLabel` | `string` | `"Blocked"` |
| `glow` | `boolean` | `true` |
| `guides` | `boolean` | `true` |
| `showLabels` | `boolean` | `true` |

## Types

```ts
interface GatewayRequest {
  icon: LucideIcon;
  label: string;
  meta?: string;
  blocked?: boolean;
}

interface GatewayTarget {
  icon: LucideIcon;
  label: string;
  meta?: string;
}
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_LOGO: React.ReactNode = (
  <ShieldCheck className="size-9" strokeWidth={1.75} />
);

const DEFAULT_REQUESTS: GatewayRequest[] = [
  { icon: Globe, label: "GET /api", meta: "203.0.113.7" },
  { icon: Bot, label: "Bot traffic", meta: "4k req/s", blocked: true },
  { icon: LogIn, label: "POST /login", meta: "198.51.100.4" },
  { icon: Webhook, label: "Webhook", meta: "Partner IP" },
];

const DEFAULT_APP: GatewayTarget = {
  icon: AppWindow,
  label: "Your app",
  meta: "Protected",
};
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import HeroSecurityGateway from "@/components/codedvisuals/hero/security-gateway";
import { Bot, Bug, Globe, LogIn, Upload, Webhook } from "lucide-react";

// default
<HeroSecurityGateway />

// hover
<HeroSecurityGateway hover />

// minimal · no labels · no guides · no glow
<HeroSecurityGateway showLabels={false} guides={false} glow={false} />

// max requests · six requests
<HeroSecurityGateway
  requests={[
    { icon: Globe, label: "GET /api", meta: "203.0.113.7" },
    { icon: LogIn, label: "POST /login", meta: "198.51.100.4" },
    {
      icon: Bot,
      label: "Bot traffic",
      meta: "4k req/s",
      blocked: true,
    },
    { icon: Webhook, label: "Webhook", meta: "Partner IP" },
    {
      icon: Bug,
      label: "SQL injection",
      meta: "Payload match",
      blocked: true,
    },
    { icon: Upload, label: "PUT /files", meta: "192.0.2.18" },
  ]}
/>
```
