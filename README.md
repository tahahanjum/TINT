# Tint

Created by **Taha Anjum**.

Tint sets your PC's RGB lighting to the main color of your wallpaper: motherboard, case fans, CPU cooler and keyboard, all at once.

1. Drop in a wallpaper, or click **Use desktop wallpaper**.
2. Tint shows the color it picked.
3. Click **Apply**.

Turn on **Live Sync** and the lights change by themselves whenever your wallpaper changes.

## Install

1. Download **`Tint-Setup.exe`** and run it. No administrator rights are needed.
2. Open **Tint** from the Start menu.

Windows 10 (1809+) or Windows 11, 64-bit. Everything the app needs is included.

For the **keyboard and Lian Li fans**, also install **[OpenRGB](https://openrgb.org)** (1.0 recommended). Tint connects to it automatically, and starts it for you if needed.

## Supported devices

| Device | How Tint controls it |
|---|---|
| **Gigabyte motherboard (RGB Fusion 2.0)**, e.g. B550M K | Directly over USB. This includes the onboard LEDs and everything plugged into the board's RGB/ARGB headers. No Gigabyte software is needed. |
| **Lian Li fans and CPU cooler** | Plugged into the motherboard's ARGB header: through the motherboard, with nothing extra needed. On a Lian Li UNI HUB / L-Connect controller: through OpenRGB, and close L-Connect so the two apps don't fight. |
| **Keyboard** (e.g. GK687) and other RGB devices | Through OpenRGB. |

Tint only reports a device as changed after the device (or OpenRGB) confirms the new color. Devices that don't answer are listed with the reason. Click **Missing a device?** in the app for setup tips.

## Using Tint

- **Adjust** (under the color) lets you change brightness, saturation and overall LED intensity, pick another color from the image, or type your own.
- **Settings** (gear icon):
  - start with Windows
  - what Live Sync follows
  - restore the color after sleep
  - which devices to include
  - save a report if something doesn't work
- **–** minimizes the window. **X** quits Tint.

## How the color is picked

Tint uses the same method as the BookMarkle extension's `color.js`:

1. It shrinks the image to 64 × 64 and skips pixels that are nearly black, nearly white or grey.
2. Each remaining pixel votes for its hue (in 15° steps). Vivid, medium-bright pixels count most.
3. The winning hue becomes the color. Its saturation and lightness are then kept within a pleasant range, and the range is different for light and dark wallpapers.

## Troubleshooting

| Problem | Fix |
|---|---|
| Motherboard shows *Unavailable* | Close RGB Fusion / GIGABYTE Control Center, then click refresh. |
| Keyboard or fans not listed | Open OpenRGB. If OpenRGB doesn't show the device, Tint can't either. Close L-Connect completely. |
| *OpenRGB reports 0 LEDs* | In OpenRGB select the device → **Zones** → set the LED count → **Resize**. |
| Color changes back | Another RGB app, or the keyboard's Fn lighting keys, is overriding it. |
| Anything else | **Settings → Save report…** and share the file. |

## License

Copyright © 2026 Taha Anjum. All rights reserved.

Tint is proprietary software. You may install and use the official installer for personal, non-commercial use. You may not fork, copy, modify, reuse, redistribute or sell Tint, its code or its assets without written permission from Taha Anjum. See [`LICENSE`](LICENSE) for the full terms.

Tint includes the .NET runtime (MIT) and SixLabors.ImageSharp (Six Labors Split License), which stay under their own licenses. OpenRGB is not included.
