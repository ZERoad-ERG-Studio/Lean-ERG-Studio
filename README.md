# ZER<sup>OAD</sup> Lean ERG Studio

**Zero fluff // max effort.**

A smart-trainer workout app in a single HTML file. Pair your trainer over Bluetooth, build or import a workout, and ride it in ERG mode. No accounts, no tracking, no server: your rides stay on your device.

> Developed and tested with an Elite Suito-T trainer, a Quarq crank power meter and a Bluetooth heart-rate strap. Other FTMS trainers and Bluetooth power meters should work, but are untested.

## Features

**Riding**
- **ERG mode**: the trainer holds the target power of the current interval.
- **SIM mode**: free ride with an adjustable grade.
- **Power meter as the reference**: pair a Bluetooth power meter and ERG steers the trainer until *the meter* shows the target power. The meter's watts are what you see, log and export. No calibration factor is stored. If the meter signal drops, the app falls back to the trainer's reading and holds the last adjustment.
- Heart-rate strap support.
- Large live readouts: power, target, cadence, heart rate, session time (elapsed / total) and interval time (elapsed / total).
- A position marker travelling along the interval graph, interval cues (beeps and a screen flash), smooth transitions between steps, screen wake lock.

**Workouts**
- Steady intervals and ramps (for example 5 min rising from 100 W to 200 W).
- Repeat blocks, undo / redo.
- Targets in watts or as % of FTP, with power-zone colours (Z1 to Z7).
- Edit durations and power directly in the graph or in the planner. Move intervals with arrows or drag and drop.
- Workout library saved on your device.
- Import and export: CSV, ZWO, MRC and ERG files.

**After the ride**
- Summary: average and normalized power, intensity factor, TSS, best 1 and 5 minutes, energy, cadence, heart rate, distance, W/kg (if you enter your weight), planned vs. actual per interval.
- History of past rides: reopen the full summary, rename a ride, load its workout again, re-download its .FIT file.
- **.FIT export** for uploading to the training platform of your choice.

**Design**
- Minimal black-and-white interface with a dark / light toggle. Fonts are embedded, so it looks the same on every device.
- Installable as an app (PWA), works offline once loaded. Phone and tablet friendly.

## Getting started

1. Open the app from an **https** address (for example GitHub Pages, see below). Web Bluetooth only works on secure pages.
2. Press **Pair trainer** and pick your trainer. Optionally pair a power meter and a heart-rate strap.
3. Enter your FTP, build or import a workout, press **Start session**.

Opening `index.html` straight from your disk also works for building workouts, and in Chrome / Edge it usually allows Bluetooth too.

### Browser support

| Platform | Browser |
|---|---|
| Windows, macOS, Linux, ChromeOS | Chrome or Edge |
| Android | Chrome |
| iPhone / iPad | Bluefy (Safari has no Web Bluetooth) |
| Firefox, Safari (desktop) | No Bluetooth. You can still build workouts. |

### Keyboard shortcuts

| Key | Action |
|---|---|
| Space | Start / pause |
| Up / Down | Nudge the target (while riding) |
| Right | Skip to the next interval |
| Ctrl+Z / Ctrl+Y | Undo / redo |

## Host it yourself (GitHub Pages)

1. Put `index.html` in the root of the repository. This single file is the whole app. Rename it if needed, because GitHub Pages opens `index.html` by default.
2. In the repository go to **Settings → Pages**, choose the branch and the root folder, and save.
3. Open the address GitHub gives you.


## Privacy

Everything is stored in your browser's local storage: settings, saved workouts, ride history and ride data. Nothing is sent anywhere. Clearing the browser's site data deletes it, so export a .FIT file of rides you want to keep. If the browser storage fills up, the oldest rides keep their summary but lose their detailed data.

## Notes

- With a power meter paired, ERG needs up to about 15 seconds to settle after a big step change (for example 180 W to 240 W), and your power may be off target for part of that time.
- The trainer is never told a wattage above 1000 W or below 40 W.
- Use at your own risk, and stop riding if something feels wrong. This is a hobby project, not a medical or coaching product.

## Technical

Single-file vanilla JavaScript, no dependencies and no build step. Bluetooth profiles used: Fitness Machine (FTMS), Cycling Power, Heart Rate.

## License

All rights reserved. Beta testing.
