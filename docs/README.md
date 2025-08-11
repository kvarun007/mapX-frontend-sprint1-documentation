# Sprint 1 – Interactive Globe Map

## 1. Feature Overview

**Goal:** Create an interactive globe map using Mapbox GL in a React + Vite + Tailwind + Material UI environment.

**Sprint 1 Scope:**

- Mapbox GL globe view with hardcoded GeoJSON polygons.
- Collapsible left & right panels.
- Timeline control at bottom with slider & year display.
- Numeric keypad modal for year input.

---

## 2. Detailed Workflow

### 2.1 Map Display

- Load Mapbox GL JS in React.
- Projection: `globe`.
- Load hardcoded GeoJSON polygon data (frontend only in Sprint 1).
- Style polygons with fill color, opacity, and border color.
- Re-render polygons on data change.

### 2.2 Collapsible Side Panels

**Initial State:**

- Left & right panels collapsed (~40px width) showing only icon.

**Expand on Click:**

- Animate width to ~300px.
- Show placeholder content ("Future Content Area").

**Collapse:**

- Click icon to shrink back.

### 2.3 Timeline at Bottom

**Layout:**

- Full-width bar fixed at bottom.
- Horizontal line with years above.
- MUI Slider handle below.

**Interaction:**

- Drag slider → update year dynamically.
- Click year → open keypad modal.

### 2.4 Year Keypad Modal

**Trigger:** Clicking year text.

**Rough Layout:**
[1] [2] [3]

[4] [5] [6]
[7] [8] [9]
[BCE] [0] [CE]
[Backspace] [Enter]

**Behavior:**

- Append digits on number click.
- Toggle BCE/CE.
- Backspace removes last digit.
- Enter → validate & update slider.
- Invalid year → SweetAlert error.

---

## 3. Technical Requirements

**Core Stack:**

- React (Vite)
- TailwindCSS
- Material UI
- Mapbox GL JS
- SweetAlert2

**Suggested Libraries:**

- framer-motion → panel/slider animations
- react-map-gl → optional Mapbox wrapper
- dayjs → BCE/CE formatting

---

## 4. File/Folder Structure

```bash
src/
<<<<<<< HEAD
  components/
    MapView.jsx
    LeftPanel.jsx
    RightPanel.jsx
    Timeline.jsx
    YearKeypadModal.jsx
  data/
    sampleGeoJSON.js
  App.jsx
  main.jsx
  index.css
```

=======
components/
MapView.jsx
LeftPanel.jsx
RightPanel.jsx
Timeline.jsx
YearKeypadModal.jsx
data/
sampleGeoJSON.js
App.jsx
main.jsx
index.css

> > > > > > > decc1474055014bccb827bdbad764dfc1283f13e

---

## 5. Data Structures

### 5.1 Sample GeoJSON (Polygon)

```js
export const samplePolygon = {
  type: "FeatureCollection",
  features: [
    {
      type: "Feature",
      properties: { name: "Sample Area" },
      geometry: {
        type: "Polygon",
        coordinates: [
          [
            [-10, 50],
            [-5, 50],
            [-5, 55],
            [-10, 55],
            [-10, 50]
          ]
        ]
      }
    }
  ]
};

5.2 Timeline Year Data

export const timelineSettings = {
  minYear: -5000, // BCE
  maxYear: 2025,  // CE
  initialYear: 0  // year displayed at start
};
```
