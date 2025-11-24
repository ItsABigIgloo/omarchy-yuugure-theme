# 🌇 Yuugure (Twilight) Theme
> A bright, narrative-driven dark mode for Hyprland.

**Yuugure** is a high-contrast, "bright dark" configuration for Hyprland on Arch Linux. It is designed to be calming without being depressing, utilizing deep blues and vibrant sunset oranges to keep energy levels high while reducing eye strain.

The theme follows a narrative visual style featuring a lone traveler and her black cat, drifting through quiet moments in a loud world.

![Hyprland Version](https://img.shields.io/badge/Hyprland-v0.40+-orange?style=flat&logo=archlinux)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)

## 🎨 The Aesthetic

**"Bright Dark" Mode:**
Instead of the standard "flat grey" dark mode, Yuugure uses deep saturation.
* **Active Focus:** Windows glow with a **Spinning Orange-to-Blue Gradient**, mimicking the transition from sunset to night.
* **Passive Immersion:** Inactive windows dim and blur slightly, allowing the wallpaper art to bleed through, creating a "frosted glass" depth effect.
* **The Colors:**
    * `#ffa500` (Sunset Orange) - Energy, Focus.
    * `#0000ff` (Deep Sea Blue) - Calm, Depth.
    * `#1e1e2e` (Midnight Base) - The canvas.

## 🖼️ The Narrative (Wallpapers)

The wallpapers tell the story of a researcher/traveler and her companion black cat.
1.  **The Commute:** Staring out a train window at the ocean (Focus Mode).
2.  **The Porch:** A quiet smoke break at a seaside cabin (Relax Mode).
3.  **The Café:** People watching in a warm coffee shop (Social Mode).

*(Wallpapers generated specifically for this theme).*

## 🛠️ Installation

### Dependencies
* **WM:** Hyprland
* **Bar:** Waybar
* **Terminal:** Kitty / Alacritty / WezTerm
* **Wallpaper Daemon:** `swww` or `hyprpaper`
* **Font:** Nerd Fonts (JetBrainsMono recommended)

### 1. Hyprland Configuration (`hyprland.conf`)
The core visual definition:

```ini
general {
    # The signature Twilight Gradient
    col.active_border = rgba(ffa500ff) rgba(0000ffff) 45deg
    col.inactive_border = rgba(595959aa)
    border_size = 2
}

decoration {
    rounding = 10
    
    # Focus Logic: Dim everything that isn't active
    dim_inactive = true
    dim_strength = 0.25
    
    # Glass Effect
    active_opacity = 1.0
    inactive_opacity = 0.90
    
    blur {
        enabled = true
        size = 4
        passes = 2
        new_optimizations = true
        ignore_opacity = true
    }
}

animations {
    enabled = yes
    # The "Spinning" Border Animation
    bezier = linear, 0.0, 0.0, 1.0, 1.0
    animation = borderangle, 1, 50, linear, loop
}
