# hyprwall

`hyprwall` is a lightweight bash script designed to simplify wallpaper management for [hyprpaper](https://github.com/hyprwm/hyprpaper) on Hyprland. It adds functionality like cycling through wallpapers, choosing random images, and automatically handling multiple monitors.

## Features

- **Cycle Wallpapers**: Move forward or backward through your wallpaper collection.
- **Randomize**: Quickly set a random wallpaper from your specified directory.
- **Multi-monitor Support**: Automatically detects active monitors and applies the wallpaper to all of them.
- **State Management**: Remembers the last used wallpaper to allow sequential cycling.
- **Intelligent Loading**: Automatically starts `hyprpaper` if it's not running and unloads unused wallpapers to save memory.

## Installation

1. Download the `hyprwall.sh` script.
2. Make it executable:
   ```bash
   chmod +x hyprwall.sh
   ```
3. (Optional) Move it to your PATH for easier access:
   ```bash
   mv hyprwall.sh ~/.local/bin/hyprwall
   ```

## Usage

```bash
hyprwall [options]
```

### Options

- `-c`: Cycle forward to the next wallpaper.
- `-p`: Cycle backward to the previous wallpaper.
- `-r`: Set a random wallpaper.
- `-w <directory>`: Specify a custom directory to search for images.
- `-i <file>`: Set a specific image file as your wallpaper.
- `-h`: Show help information.

### Examples

**Set a random wallpaper from default locations:**
```bash
hyprwall -r
```

**Cycle to the next wallpaper in a specific folder:**
```bash
hyprwall -w ~/Pictures/Nature -c
```

**Set a specific image:**
```bash
hyprwall -i ~/Pictures/Wallpapers/mountain.jpg
```

## Default Search Directories

If no directory is specified with `-w`, `hyprwall` will search for images in the following locations:
- `~/Wallpapers`
- `~/Pictures/Wallpapers`
- `~/Pictures/wallpaper`
- `~/.config/wallpapers`

## Integration with Hyprland

You can bind `hyprwall` to keybindings in your `hyprland.conf`:

```ini
bind = $mainMod, W, exec, hyprwall -r
bind = $mainMod SHIFT, W, exec, hyprwall -c
```
