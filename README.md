# Material 3 Expressive — Voidstrap Custom Bootstrapper Theme

[![Material Design 3](https://img.shields.io/badge/Design-Material%203%20(Material%20You)-6750A4?style=for-the-badge&logo=google)](https://m3.material.io/)
[![Release v1.0.0](https://img.shields.io/badge/Release-v1.0.0-blue?style=for-the-badge)](releases)
[![Voidstrap Compatible](https://img.shields.io/badge/Voidstrap-Compatible-00C853?style=for-the-badge)](https://github.com/KloBraticc/Voidstrap)
[![Platform Windows](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078D6?style=for-the-badge&logo=windows)](https://microsoft.com/windows)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

An expressive, modern **Google Material 3 (Material You)** custom bootstrapper theme for **[Voidstrap](https://github.com/KloBraticc/Voidstrap)**. Built with dynamic Windows accent color synchronization, intelligent WCAG luminance contrast, atmospheric tonal surfaces, and fluid micro-animations.

---

## Voidstrap

This theme is designed exclusively for **Voidstrap**, an open-source, feature-packed custom Roblox bootstrapper:
- **Repository**: https://github.com/KloBraticc/Voidstrap

---

## Features

- **Live Windows Accent Color Sync**: Automatically reads your active Windows accent color directly from Windows Settings (`HKCU:\Software\Microsoft\Windows\DWM\AccentColor`) and updates the entire UI in real-time without restarting the app.
- **Material You Tonal Tinting**: Rather than flat black or grey backgrounds, the theme dynamically synthesizes deep, atmospheric dark tonal surfaces (Tone 6, Tone 10, Tone 18) tinted with your accent hue.
- **Smart WCAG Contrast**: Employs real-time relative luminance calculation:
  - **Light/White accents** $\rightarrow$ Crisp black text (`#000000`).
  - **Dark/Black accents** $\rightarrow$ Clean white text (`#FFFFFF`).
- **Expressive M3 Components**:
  - **M3 Pill Cancel Button**: Elevated interactive button styled with your brightened accent color and high-contrast text.
  - **Floating Squircle Avatar**: Clean, glow-free logo container with subtle drop shadows and interactive tactile bounce.
  - **Dynamic Progress Bar**: Smooth percentage transitions with indeterminate shimmer effect and a pill-shaped percentage badge.
- **Fluid Transitions**: All color transitions run with smooth CSS transitions (`0.35s ease`), allowing live morphing as you change Windows colors.
- **Startup Audio Support**: Optional startup sound playback upon launch.

---

## Preview

<p align="center">
  <img src="https://files.catbox.moe/ps6viy.png" alt="Material 3 Preview 1" width="48%" />
  <img src="https://files.catbox.moe/2h7s8u.png" alt="Material 3 Preview 2" width="48%" />
</p>
<p align="center">
  <img src="https://files.catbox.moe/7xfc2n.png" alt="Material 3 Preview 3" width="48%" />
  <img src="https://files.catbox.moe/4wleff.png" alt="Material 3 Preview 4" width="48%" />
</p>

---

## Repository Structure

```text
Material3/
├── Theme.xml          # Voidstrap XML theme configuration (window size, borders, engine)
├── index.html         # Semantic Material 3 markup structure
├── style.css          # Material You CSS design tokens & animations
├── app.js             # Dynamic color extraction, contrast engine & live watcher
├── accent.json        # Auto-synced color cache for the bootstrapper
├── icon.png           # Theme icon preview
├── icon.ico           # Application icon
├── icons/             # Custom & classic Roblox era icons
├── LICENSE            # MIT License
├── .gitignore         # Git ignore rules
└── README.md          # Project documentation
```

---

## Installation & Setup

### Method 1: Automatic / Direct Copy
1. Press <kbd>Win</kbd> + <kbd>R</kbd>, type `%localappdata%\Voidstrap\Themes\Custom`, and press **Enter**.
2. Clone or download this repository into that folder as a folder named `Material3`:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Material3.git "%localappdata%\Voidstrap\Themes\Custom\Material3"
   ```
3. Open **Voidstrap** ([https://github.com/KloBraticc/Voidstrap](https://github.com/KloBraticc/Voidstrap)).
4. Navigate to **Appearance** $\rightarrow$ **Bootstrapper Style**.
5. Select **Custom**, then choose **Material3** from the dropdown list.
6. Click **Save** and preview the theme.

---

## How Live Accent Theming Works

1. **Registry Detection**: Windows stores the current personal accent color in:
   ```powershell
   Get-ItemPropertyValue -Path "HKCU:\Software\Microsoft\Windows\DWM" -Name "AccentColor"
   ```
2. **Dynamic Palette Synthesis**:
   - The theme reads the hex color and converts it to HSL color space.
   - The accent lightness is boosted by ~20%–35% for expressive pastel clarity.
   - The background surfaces are tinted with low-lightness variants of your accent hue.
   - Relative luminance formula ($Y = 0.2126R + 0.7152G + 0.0722B$) dynamically selects `#000000` or `#FFFFFF` for button and badge text.
3. **Live Sync**:
   - The theme continuously polls and listens for color updates every 300ms, immediately updating CSS variables (`--md-sys-color-primary`, `--md-sys-color-surface`, etc.) with zero flicker.

---

## Configuration & Customization

You can tweak parameters inside `app.js` and `style.css`:

- **Window Dimensions**: Adjust `Width` and `Height` in `Theme.xml` (default: `540x320`).
- **Accent Lightness**: Modify the `lightenRgb()` function in `app.js` to change how bright primary accents appear.
- **Surface Tone Depth**: Modify the `getM3TonalSurfaces()` lightness values in `app.js` to make surfaces darker or more saturated.

---

## Contributing

Contributions, feedback, and issue reports are always welcome.
- Fork the repository.
- Create a feature branch (`git checkout -b feature/MyFeature`).
- Commit your changes (`git commit -m "Add expressive ripple effect"`).
- Push to the branch (`git push origin feature/MyFeature`).
- Open a Pull Request.

---

## License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

<p align="center">
  Crafted for the <a href="https://github.com/KloBraticc/Voidstrap"><b>Voidstrap</b></a> community.
</p>
