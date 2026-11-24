# Garmin 360° Vehicle Sprite & .SRF Generator

A browser-based tool that turns a bird's-eye vehicle image (or existing `.srf` file) into a 36-angle (10° increments) sprite sheet and a ready-to-use Garmin `.srf` vehicle icon—without requiring external command-line utilities like `png2srf`.

- **Live App:** [https://hightechum.github.io/garmin-srf-generator/](https://hightechum.github.io/garmin-srf-generator/)
- **Source Code:** [https://github.com/hightechum/garmin-srf-generator](https://github.com/hightechum/garmin-srf-generator)
- **Issues & Feature Requests:** [https://github.com/hightechum/garmin-srf-generator/issues](https://github.com/hightechum/garmin-srf-generator/issues)

---

## Features

- **100% Client-Side Processing:** Background removal, 36-step rotation, previewing, and `.srf` encoding run locally in your browser with no server uploads or tracking.
- **Multiple Input Formats:** Upload `PNG`, `JPG`, `WEBP`, or an existing Garmin `.SRF` file via drag-and-drop or file picker.
- **Background Cleanup Controls:** Adjust **Background Removal Tolerance** (default `35`), toggle **Edge flood-fill only** to preserve inner white highlights, and scale the vehicle with **Vehicle Size in Tile (%)** (default `88%`).
- **Orientation & Rotation Controls:** Rotate in `90° L` / `90° R` increments, choose **Initial Angle Offset** (`0°`, `180°`, `90° Right`, `90° Left`), and select **Clockwise** or **Counter-Clockwise** rotation across 36 angles (`10°` steps).
- **Garmin Format Support:**
  - **Standard 3D + 2D Overhead (`2881 × 160` / `v2.00`)** for broad compatibility.
  - **Newer Garmin `80×80` + `70×70` (`2880 × 150` / `v2.20`)** for newer units where `v2.00` may appear stretched or blank in 2D overhead view.
- **Live Preview & Exports:** Inspect the cropped transparent sprite, watch a slow `360°` preview, scroll through all 36 frames on the generated sprite sheet, and export `.srf` or `.png` (including a new-tab fallback for restricted iframe/download environments).

---

## How to Create & Install a Garmin .SRF Vehicle Icon

1. **Upload an image:** Drag and drop or select a top-down vehicle image (`PNG`, `JPG`, `WEBP`) or `.SRF` file. A clean overhead image with a transparent or solid background gives the cleanest cutout.
2. **Tune metadata & cutout:** Set optional vehicle details (**Color**, **Make**, **Model**) and **Export Filename**, then adjust **Background Removal Tolerance**, **Edge flood-fill only**, and **Vehicle Size in Tile (%)** as needed.
3. **Align & preview:** Use the **90° L / 90° R** controls, **Initial Angle Offset**, and **Rotation Direction** so the front of the vehicle points straight up (North) along the arrow guide, and verify the **360° Preview** and **Generated Sprite Sheet**.
4. **Export `.srf`:** Choose **v2.00** or **v2.20** and download your `.srf` file (or `.png` sprite sheet).
5. **Install on your Garmin GPS:**
   - Connect your Garmin device to your computer via USB.
   - Back up your existing `\Garmin\Vehicle\` folder.
   - Copy the new `.srf` file into `\Garmin\Vehicle\`.
   - Safely eject the device and select your custom vehicle under **Settings > Map & Vehicle > Vehicle**.

---

## Compatibility & Privacy Notes

- **Supported Devices:** Most Garmin automotive GPS units with a `Vehicle` folder (such as Drive, DriveSmart, DriveAssist, and older nüvi models) support custom `.srf` icons.
- **Privacy:** All image processing and binary `.srf` generation happen locally in the browser; no files or telemetry are sent to a remote server.
