---
name: codedvisuals-geo-edge-network
description: A dotted world map where a request hops to the nearest edge node, with latency chips comparing the edge to a distant origin server. The Edge Network visual in the Geo category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Geo / Edge Network

A dotted world map where a request hops to the nearest edge node, with latency chips comparing the edge to a distant origin server.

- **Registry name:** `@codedvisuals/geo-edge-network`
- **Import path:** `@/components/codedvisuals/geo/edge-network`

## Install if it is not in the project yet

Look for `components/codedvisuals/geo/edge-network.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/geo-edge-network
```

This uses the private registry (one time setup) and installs Motion and lucide-react if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`) and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `user` | `EdgeNetworkLocation` | see Default content below |
| `edges` | `EdgeNetworkLocation[]` | see Default content below |
| `origin` | `EdgeNetworkLocation` | see Default content below |
| `compare` | `boolean` | `true` |
| `latency` | `number` | - |
| `originLatency` | `number` | - |
| `density` | `EdgeNetworkDensity` | `"normal"` |
| `wrapperClassName` | `string` | - |

## Types

```ts
interface EdgeNetworkLocation {
  lat: number;
  lng: number;
  label?: string;
}

type EdgeNetworkDensity = "sparse" | "normal" | "dense";
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_USER: EdgeNetworkLocation = {
  lat: 38.72,
  lng: -9.14,
  label: "Lisbon",
};

const DEFAULT_EDGES: EdgeNetworkLocation[] = [
  { lat: 37.77, lng: -122.42, label: "San Francisco" },
  { lat: -23.55, lng: -46.63, label: "Sao Paulo" },
  { lat: 51.51, lng: -0.13, label: "London" },
  { lat: -26.2, lng: 28.05, label: "Johannesburg" },
  { lat: 19.08, lng: 72.88, label: "Mumbai" },
  { lat: 1.35, lng: 103.82, label: "Singapore" },
  { lat: 35.68, lng: 139.69, label: "Tokyo" },
  { lat: -33.87, lng: 151.21, label: "Sydney" },
];

const DEFAULT_ORIGIN: EdgeNetworkLocation = {
  lat: 39.04,
  lng: -77.49,
  label: "Origin",
};
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import GeoEdgeNetwork from "@/components/codedvisuals/geo/edge-network";

// default
<GeoEdgeNetwork />

// hover
<GeoEdgeNetwork hover />

// no compare
<GeoEdgeNetwork compare={false} />

// custom latency
<GeoEdgeNetwork latency={8} originLatency={240} />

// user in Seoul
<GeoEdgeNetwork user={{ lat: 37.57, lng: 126.98, label: "Seoul" }} />

// user in Cape Town
<GeoEdgeNetwork user={{ lat: -33.92, lng: 18.42, label: "Cape Town" }} />

// custom edges · origin in Frankfurt
<GeoEdgeNetwork
  user={{ lat: 41.88, lng: -87.63, label: "Chicago" }}
  edges={[
    { lat: 47.61, lng: -122.33, label: "Seattle" },
    { lat: 32.78, lng: -96.8, label: "Dallas" },
    { lat: 43.65, lng: -79.38, label: "Toronto" },
    { lat: 25.76, lng: -80.19, label: "Miami" },
    { lat: 19.43, lng: -99.13, label: "Mexico City" },
    { lat: 48.86, lng: 2.35, label: "Paris" },
    { lat: 1.35, lng: 103.82, label: "Singapore" },
  ]}
  origin={{ lat: 50.11, lng: 8.68, label: "Frankfurt" }}
/>

// sparse
<GeoEdgeNetwork density="sparse" />

// dense
<GeoEdgeNetwork density="dense" />
```
