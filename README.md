# ZER<sup>O</sup><sup>AD</sup> Lean ERG Studio

**Zero fluff // max effort.**

A smart-trainer workout app in a single HTML file. Pair your trainer over Bluetooth, build or import a workout, and ride it in ERG mode. No accounts, no tracking, no server: your rides stay on your device.

> Developed and tested with an Elite Suito-T trainer, a Quarq crank power meter and a Bluetooth heart-rate strap. Other FTMS trainers and Bluetooth power meters should work, but are untested. ZEROAD is not affiliated with any brand named here.

**Open the app:** https://zeroad-erg-studio.github.io/Lean-ERG-Studio/

## Features

**Riding**
- **ERG mode**: the trainer holds the target power of the current interval.
- **SIM mode**: free ride with an adjustable grade.
- **Power meter as the reference**: pair a Bluetooth power meter and ERG steers the trainer until *the meter* shows the target power. The meter's watts are what you see, log and export. No calibration factor is stored. If the meter signal drops, the app falls back to the trainer's reading and holds the last adjustment.
- **Max effort steps**: an all-out interval with no target power. The trainer gives a fixed low resistance (set in Settings), and the summary shows your peak power for the effort.
- **Cadence ranges** in intervals (for example 90-100 rpm), with a clear cue when you are outside the range.
- **Auto-pause** (optional): the timer stops after 5 seconds without pedalling and resumes when you pedal again.
- **Spoken cues** (optional): the interval and its target are read out when it starts, and what comes next 10 seconds before the end.
- Speed and distance are calculated from your power (rider weight plus a 9 kg bike, flat road in ERG, the set grade in SIM), because a trainer's own speed follows cadence rather than power in ERG mode. They are estimates.
- Large live readouts: power, target, cadence, heart rate (with zone), session time and interval time, each as elapsed / total.
- Interval cues (beeps and a screen flash), smooth transitions, screen wake lock, a full-screen mode with only the numbers and the graph.
- **Restore an interrupted ride** after a crash, a closed tab or a dead battery.

**Workouts**
- Steady intervals and ramps (for example 5 min rising from 100 W to 200 W).
- Repeat blocks, undo / redo.
- Targets in watts or as % of FTP, with power-zone colours (Z1 to Z7).
- Edit durations, power and cadence directly in the graph or in the planner. Move intervals with arrows or drag and drop.
- Starter workouts (endurance, tempo, sweet spot, threshold, VO2 max, sprints) and your own workout library.
- Import and export: CSV, ZWO, MRC and ERG files.
- **FTP tests**: a 20-minute test and a ramp test. The app estimates your FTP from the ride and offers to save it.

**After the ride**
- Summary: average and normalized power, intensity factor, TSS, best 1 and 5 minutes, energy, cadence, heart rate and heart-rate zones, distance, W/kg (if you enter your weight), planned vs. actual per interval.
- History of past rides: reopen the full summary, rename a ride, load its workout again, re-download its .FIT file.
- **.FIT export**, and a **Send to Strava** button that downloads the .FIT file and opens Strava's upload page. The activity title ("ZERoad: Workout name") is copied to your clipboard to paste.
- **Trainer check**: compares the trainer's own reading with your power meter across your rides. It only reports; nothing is corrected.

**Settings**
- Rider: FTP, weight, maximum heart rate, metric or imperial units.
- Riding: smooth transitions, auto-pause, max effort resistance.
- Cues: sound and spoken cues.
- Display: dark or light theme.
- Data: back up everything to a file, restore it, or delete all data.

**Design**
- Minimal black-and-white interface. Fonts are embedded, so it looks the same on every device.
- Installable as an app (PWA), works offline once loaded. Phone and tablet friendly.

## Getting started

1. Open the app from an **https** address. Web Bluetooth only works on secure pages.
2. Press **Pair trainer** and pick your trainer. Optionally pair a power meter and a heart-rate strap.
3. Open **Settings** and enter your FTP, then pick a starter workout or build your own and press **Start session**.

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
| Up / Down | Nudge the target (grade in SIM) while riding |
| Right | Skip to the next interval |
| Ctrl+Z / Ctrl+Y | Undo / redo |

## Host it yourself (GitHub Pages)

1. Put `index.html` in the root of the repository. This single file is the whole app.
2. In the repository go to **Settings → Pages**, choose the branch and the root folder, and save.
3. Open the address GitHub gives you.

Optional, for installing the app and using it offline: also add `manifest.webmanifest`, `sw.js`, `icon-192.png` and `icon-512.png` next to `index.html`.

## Privacy

Everything is stored in your browser's local storage: settings, saved workouts, ride history and ride data. Nothing is sent anywhere. The only thing that leaves your device is a .FIT file that you choose to upload to Strava yourself. Clearing the browser's site data deletes everything, so use **Settings → Back up to file** and export .FIT files of rides you want to keep.

## Notes

- With a power meter paired, ERG needs up to about 15 seconds to settle after a big step change (for example 180 W to 240 W).
- The trainer is never told a wattage above 1000 W or below 40 W.
- Use at your own risk, and stop riding if something feels wrong. This is a hobby project, not a medical or coaching product.

## Support

Contact: zero.fluff.fuel@gmail.com · Support the project: https://buymeacoffee.com/zero.fluff.fuel

## Technical

Single-file vanilla JavaScript, no dependencies and no build step. Bluetooth profiles used: Fitness Machine (FTMS), Cycling Power, Heart Rate.

## Licence and fonts

&copy; 2026 Aljaž Seničar &middot; ZER<sup>O</sup> family. All rights reserved. Free for public use; copying, modifying or redistributing the code needs written permission.

Embedded fonts: Montserrat (Copyright 2024 The Montserrat.Git Project Authors) and Roboto Mono (Copyright 2015 The Roboto Mono Project Authors), both under the SIL Open Font License, Version 1.1 (https://openfontlicense.org).
