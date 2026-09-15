# Tint

Created by **Taha Anjum**.

Tint sets your PC's RGB lighting to the main color of your wallpaper. It changes the motherboard, case fans, CPU cooler and keyboard together.

1. Drop in a wallpaper, or click **Use desktop wallpaper**.
2. Tint shows the color it picked.
3. Click **Apply**.

Turn on **Live Sync** and the lights change by themselves whenever your wallpaper changes.

## Install

1. Download **`Tint-Setup.exe`** and run it. No administrator rights are needed.
2. Open **Tint** from the Start menu.

That's all. **Nothing else needs to be installed**, because Tint includes everything it needs, including its keyboard and fan support.

Requires Windows 10 (1809+) or Windows 11, 64-bit.

## Supported devices

| Device | How Tint controls it |
|---|---|
| **Gigabyte motherboard (RGB Fusion 2.0)**, e.g. B550M K | Directly over USB. This covers the onboard LEDs and everything plugged into the board's RGB/ARGB headers. |
| **Lian Li fans and CPU cooler** | Plugged into the motherboard's ARGB header: through the motherboard. On a Lian Li UNI HUB (SL, AL, SL V2, AL V2, SL Infinity) or Strimer: through Tint's built-in device support. Close L-Connect so the two apps don't fight. |
| **Keyboards** and other RGB devices (RAM, GPUs, LED strips…) | Through Tint's built-in device support, which covers hundreds of models. |

Tint only reports a device as changed after the device confirms the new color. Devices that don't respond are listed with the reason, and **Missing a device?** in the app gives setup tips.

## Using Tint

- **Adjust** (under the color) lets you change the brightness, saturation and overall LED intensity. You can also pick another color from the image or type your own.
- **Settings** (gear icon) has these options:
  - Start with Windows
  - What Live Sync follows
  - Restore the color after sleep
  - Which devices to include
  - Save a report if something doesn't work
- **–** minimizes the window, and **X** quits Tint.

## How the color is picked

Tint uses the same method as the BookMarkle extension's `color.js`.

1. It shrinks the image to 64 × 64 and skips pixels that are nearly black, nearly white or grey.
2. Each remaining pixel votes for its hue in 15° steps. Vivid, medium-bright pixels count the most.
3. The winning hue becomes the color. Its saturation and lightness are kept within a pleasant range, which differs for light and dark wallpapers.

## Troubleshooting

| Problem | Fix |
|---|---|
| Motherboard shows *Unavailable* | Close RGB Fusion / GIGABYTE Control Center, then click refresh. |
| Fans on a Lian Li hub don't change | Close L-Connect completely (including its icon near the clock), then click refresh. Wireless Lian Li fans may not be supported. |
| Keyboard isn't listed | Plug it straight into the PC rather than through a hub, close its own lighting app, and click refresh. |
| Color changes back | Another RGB app, or the keyboard's Fn lighting keys, is overriding it. |
| Anything else | Go to **Settings → Save report…** and share the file. |

## License

Copyright © 2026 Taha Anjum. All rights reserved.

Tint is proprietary software. You may install and use the official installer for personal, non-commercial use. You may not fork, copy, modify, reuse, redistribute or sell Tint, its code or its assets without written permission from Taha Anjum. See [`LICENSE`](LICENSE) for the full terms.

Tint includes third-party components that keep their own licenses:

- The .NET runtime (MIT).
- SixLabors.ImageSharp (Six Labors Split License).
- **OpenRGB 1.0**, which provides the keyboard and fan support. It's included unmodified under the GNU GPL v2. Its license and source link are in the `openrgb` folder of the installation, and its source code is at <https://github.com/CalcProgrammer1/OpenRGB/tree/release_1.0>.
