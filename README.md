# Planum

**Experimental.** Prototype (v0.24.0). Not validated for survey, compliance or QA work.

Planum connects a Bosch Bluetooth laser meter to an Android phone. Take readings from the phone, save photos with the reading written into the file, scan surface profiles on a slider, and record floor profiles with a two-foot carriage (dipstick). Formerly *Measure Up*.

**Open the app:** https://volkov596.github.io/planum/

## What it does

- **Spot:** take a reading from the phone, or log readings taken with the meter's own button. Works with distance, continuous, angle, level, indirect height and indirect length modes.
- **Photos with measurements:** each photo carries its distance, angle, tilt, meter model and time inside the file. You can then measure from pixels in [Markup](https://volkov596.github.io/markup/) or [Digital Crack Gauge](https://volkov596.github.io/digitalcrackgauge/).
  - *Full quality:* uses the phone's camera app; the reading is stored as XMP.
  - *In browser:* the photo is taken right after the reading; the reading is stored as EXIF.
- **Scan:** repeated distance readings while the meter moves on a slider, with a built-in profile chart and one CSV per scan.
- **Profile (dipstick):** level-mode readings on a two-foot carriage. Steps are captured automatically. It also offers a zero check by 180° reversal, return walks with closure and an averaged profile, and comparison of two walks.
- **Files:** CSV export for readings, scans and profiles. Everything stays on the phone; nothing is sent to a server.

## Requirements

- **Meter:** Bosch GLM 50-27 CG or GLM 100-25 C (both tested). Other Bosch GLM "C" models with Bluetooth will likely work but are untested.
- **Phone:** Android with **Chrome**, which provides Web Bluetooth. iPhone and Firefox are not supported.
- **Install:** none. The app runs from GitHub Pages.

## Quick start

1. Turn on the meter and its Bluetooth.
2. Open the app link in Chrome on Android.
3. Tap **Connect** and pick the meter from the list.
4. Choose a tab (**Spot**, **Profile** or **Scan**) and tap the big button.

The **?** button opens the in-app Guide. After an update, add `?v=` plus any number to the link to skip the cache, and check the version at the bottom of the page.

## Status and known limits

- Uses an **undocumented Bluetooth protocol**, worked out by testing. A meter firmware update could break it.
- Tested with one phone (Motorola) and one unit of each meter.
- **Distance:** Bosch specifies ±1.5 mm. Repeat readings scatter by about 0.1 mm at short range and about 0.8 mm at 13–27 m. Accuracy against a reference has not been checked yet.
- **Scan rate:** about 2.5 readings/s on the 50-27 CG and about 1.2/s on the 100-25 C. Keep the app on screen during a scan; Chrome slows it in the background.
- **Dipstick:** results come from early field tests only and have not been checked against a level and staff. No F<sub>F</sub>/F<sub>L</sub> numbers are calculated, and nothing in the app is ASTM E1155 compliant.
- Area, volume, double-indirect and trapezoid results are not logged.
- The app only sends read and measure commands. It never changes meter settings, clears its memory or updates firmware.

## Licence

© 2026 Egor Volkov. All rights reserved. The app is free to use. Copying, modifying or redistributing the code needs the author's written permission. See `LICENSE.txt`.

## Disclaimer

This is an independent project, not affiliated with or endorsed by Bosch. Bosch and GLM are trademarks of Robert Bosch GmbH. It is provided as is, with no warranty, and you use it at your own risk.

The lasers are Class 2: don't look into the beam or point it at people.

## Feedback

Report bugs through this repo's Issues tab, or use **Report a bug** in the app (the ⓘ button).
