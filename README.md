
# Online Ender Slicer

A browser-based 3D slicer, G-code previewer, and Ender 3 controller built as a single HTML web app.

Online Ender Slicer lets you load 3D models, arrange them on a virtual build plate, generate basic G-code, inspect/edit toolpaths, run calibration generators, and connect to a printer using Web Serial or WebUSB-style fallback controls.

> ⚠️ **Safety warning:** This app can move printer motors and heat the nozzle/bed. Always supervise your printer, inspect generated G-code in a trusted viewer, and make sure the model fits your build plate before printing.

---

## Features

### Model loading

- Import `.stl`, `.obj`, `.gcode`, `.gc`, and `.zip` files
- Drag-and-drop upload area
- ZIP import support for the first compatible file inside the archive
- Multi-model build plate support
- Duplicate, delete, center, drop-to-bed, mirror, scale, rotate, and move models
- Auto-arrange models on the build plate
- Scale-to-fit tools for Ender-style beds

### Slicing controls

- Layer height and first-layer height
- Nozzle / line width
- Wall count
- Top and bottom layers
- Infill percentage
- Infill patterns:
  - Lines
  - Grid
  - Triangles
  - Gyroid-ish
- Print speed
- First-layer speed
- Travel speed
- Flow percentage
- Nozzle temperature
- Bed temperature
- Fan percentage
- Retraction distance
- Filament diameter
- Z-hop
- Skirt loops
- Brim width
- Seam mode controls

### Presets

- Print profile presets
- Material presets
- Printer presets
- Save and reset settings
- Import/export settings

### 3D preview

- Interactive model viewer
- Build plate preview
- Layer preview
- G-code path preview
- Travel move preview
- Support guide preview
- Top/front/isometric view buttons
- Snapshot export

### G-code tools

- Generate G-code from loaded models
- Upload existing G-code
- Copy G-code
- Download G-code
- Preview edited G-code
- Clear generated output
- Insert pause at a selected layer
- Insert filament change command
- Extract a specific layer
- Send extracted layer
- Download print/quality report

### Calibration generators

- Bed level test
- Temperature tower
- Retraction tower
- Flow cube
- Speed tower
- Purge line only

### Printer connection

- Web Serial connection
- WebUSB fallback option
- Disconnect control
- Baud rate selection:
  - `115200`
  - `250000`
- Strip comments before streaming
- Start print
- Pause
- Resume
- Emergency stop
- Manual command sender
- Macro save/delete tools

### Diagnostics and validation

- Model validation
- G-code validation
- Connection status
- Bed fit check
- Overhang analysis
- Startup tests
- Quality report
- Warning and idea panel
- Crash-safe UI binding

---

## Tech stack

- HTML
- CSS
- JavaScript
- Three.js
- STLLoader
- OBJLoader
- JSZip
- Web Serial API
- WebUSB-compatible fallback logic

The app is currently designed as a single-page static web project, so it can run from a browser without a backend server.

---

## Getting started

### Option 1: Open locally

1. Download or clone the repository.
2. Open `index.html` in a modern Chromium-based browser.
3. Load an STL, OBJ, G-code, or ZIP file.
4. Adjust slicing and printer settings.
5. Preview the result before downloading or streaming.

### Option 2: Clone the repo

```bash
git clone https://github.com/kai9987kai/Online-Ender-Slicer.git
cd Online-Ender-Slicer
````

Then open:

```bash
index.html
```

For the best printer connection support, use Chrome, Edge, or another browser with Web Serial support.

---

## Browser support

Recommended:

* Google Chrome
* Microsoft Edge
* Chromium-based browsers

Some features may not work in all browsers:

| Feature                       | Browser support          |
| ----------------------------- | ------------------------ |
| 3D preview                    | Most modern browsers     |
| File import                   | Most modern browsers     |
| ZIP import                    | Most modern browsers     |
| Web Serial printer connection | Chromium-based browsers  |
| WebUSB fallback               | Browser/device dependent |

---

## Basic workflow

1. Open the app.
2. Drop in an `.stl`, `.obj`, `.gcode`, `.gc`, or `.zip` file.
3. Arrange the model on the build plate.
4. Choose printer, material, and print presets.
5. Adjust slicer settings.
6. Run **Analyze** or **Check bed fit**.
7. Click **Slice model**.
8. Preview the G-code.
9. Download the G-code or connect to the printer.
10. Print only after confirming the machine is safe and supervised.

---

## Printer safety checklist

Before sending G-code to a real printer:

* Confirm the correct printer profile is selected.
* Confirm the bed size matches your printer.
* Check that the model fits on the build plate.
* Inspect the first layer.
* Check temperatures for your filament.
* Preview the generated G-code in another trusted viewer.
* Keep the printer supervised.
* Be ready to use emergency stop.

---

## Project structure

```text
Online-Ender-Slicer/
├── index.html
├── README.md
├── LICENSE
├── CODE_OF_CONDUCT.md
└── SECURITY.md
```

---

## Known limitations

This project is experimental and browser-based. It is useful for learning, testing, previewing, calibration, and lightweight slicing workflows, but it should not be treated as a replacement for mature slicers such as Cura, PrusaSlicer, OrcaSlicer, or SuperSlicer.

Current limitations may include:

* Simplified slicing compared with professional slicers
* Browser performance limits on very large models
* Printer connection support depends on browser and operating system
* Web Serial/WebUSB access may require HTTPS or local browser permissions
* Generated G-code should always be checked before printing

---

## Development notes

The project is currently built as a standalone `index.html` file. No build step is required.

To improve the project, possible next steps include:

* Split JavaScript into modules
* Add automated tests
* Add better slicer geometry handling
* Add more printer profiles
* Add saved custom profiles
* Add real support generation
* Add stronger G-code validation
* Add progress reporting during slicing
* Add offline/PWA support
* Add GitHub Pages deployment

---

## Contributing

Contributions are welcome.

Suggested contribution areas:

* UI improvements
* Better slicing algorithms
* More printer presets
* More calibration generators
* G-code validation improvements
* Documentation
* Bug fixes
* Browser compatibility testing

Before contributing, please read the code of conduct and security policy included in the repository.

---

## Security

This project interacts with local files and may communicate with connected 3D printers through browser APIs. Do not run unknown or untrusted modified versions of the app.

Report security issues using the repository security policy.

---

## License

This project is licensed under the GPL-3.0 License.

See `LICENSE` for details.

---

## Disclaimer

This software is provided as-is. 3D printers can cause burns, mechanical damage, fire risk, and hardware damage if used incorrectly. Always supervise your printer and verify all G-code before printing.

```
::contentReference[oaicite:1]{index=1}
```

[1]: https://raw.githubusercontent.com/kai9987kai/Online-Ender-Slicer/main/README.md "raw.githubusercontent.com"
