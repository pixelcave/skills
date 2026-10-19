---
name: codedvisuals-geo-geofence
description: A softly faded street map with a drawn zone, tracked devices driving its irregular roads, and a toast that pops each time one enters the zone. The Geofence visual in the Geo category of CodedVisuals. Use when adding this visual to a marketing or landing page.
---

# Geo / Geofence

A softly faded street map with a drawn zone, tracked devices driving its irregular roads, and a toast that pops each time one enters the zone.

- **Registry name:** `@codedvisuals/geo-geofence`
- **Import path:** `@/components/codedvisuals/geo/geofence`

## Install if it is not in the project yet

Look for `components/codedvisuals/geo/geofence.tsx` under the project's source root. If it is already there, just import it. If not, add it with the shadcn CLI:

```bash
npx shadcn@latest add @codedvisuals/geo-geofence
```

This uses the private registry (one time setup) and installs Motion and lucide-react if needed. See `SKILL.md` for the full setup and the copy and paste path, and `manual-setup.md` for projects without shadcn/ui.

## Props

Also supports the shared animation props (`animated`, `trigger`, `hover`), the presentation modifier (`isometric`), and `className`, all documented in `SKILL.md`. Every prop is optional and falls back to a sensible default.

| Prop | Type | Default |
| --- | --- | --- |
| `zone` | `GeofenceZone` | see Default content below |
| `devices` | `GeofenceDevice[]` | see Default content below |

## Types

```ts
interface GeofenceZone {
  area?: GeofenceArea;
  label?: string;
  detail?: string;
}

interface GeofenceDevice {
  label: string;
  route?: GeofenceRoute;
  color?: string;
}

type GeofenceArea = "downtown" | "midtown" | "west-end" | "park";

type GeofenceRoute =
  | "ring"
  | "crosstown"
  | "northeast"
  | "avenue"
  | "west-block"
  | "east-block"
  | "outskirts";
```

## Default content

The values used when you do not pass the matching prop:

```ts
const DEFAULT_ZONE = { area: "downtown" } satisfies GeofenceZone;

const DEFAULT_DEVICES: GeofenceDevice[] = [
  { label: "Van 12", route: "ring" },
  { label: "Courier 4", route: "crosstown" },
  { label: "Truck 7", route: "northeast" },
];
```

## Examples

Give the visual a sized container, then drop it in:

```tsx
import GeoGeofence from "@/components/codedvisuals/geo/geofence";

// default
<GeoGeofence />

// hover
<GeoGeofence hover />

// custom copy
<GeoGeofence
  zone={{ label: "Warehouse", detail: "250 m" }}
  devices={[
    { label: "Driver 3" },
    { label: "Forklift 2" },
    { label: "Drone 1" },
  ]}
/>

// midtown zone
<GeoGeofence zone={{ area: "midtown" }} />

// midtown zone · isometric
<GeoGeofence isometric zone={{ area: "midtown" }} />

// west end zone
<GeoGeofence zone={{ area: "west-end" }} />

// park zone
<GeoGeofence zone={{ area: "park" }} />

// device colors
<GeoGeofence
  devices={[
    { label: "Van 12", route: "ring", color: "text-sky-500" },
    {
      label: "Courier 4",
      route: "crosstown",
      color: "text-violet-500",
    },
    {
      label: "Truck 7",
      route: "northeast",
      color: "text-amber-500",
    },
  ]}
/>

// custom routes
<GeoGeofence
  devices={[
    { label: "Van 12", route: "west-block" },
    { label: "Courier 4", route: "avenue" },
    { label: "Truck 7", route: "outskirts" },
  ]}
/>

// single device
<GeoGeofence devices={[{ label: "Bike 21", route: "east-block" }]} />
```
