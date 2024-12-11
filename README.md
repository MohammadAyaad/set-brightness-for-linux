# `set_brightness` - A Script to Manage Display Brightness on Linux

## Overview

`set_brightness` is a simple bash script for managing the brightness of displays on Linux systems. It interacts with the `/sys/class/backlight` directory, allowing you to:
- View the current brightness of a display.
- Adjust the brightness using a floating-point value between `0.0` and `1.0`, which will be dynamically scaled to the display's maximum brightness value.

## Prerequisites

- Linux-based system with access to the `/sys/class/backlight` directory.
- Sudo or root privileges to modify display brightness files.

## Usage

The script allows you to:
1. Display a list of available displays.
2. Show the current brightness of a specified display.
3. Set a new brightness level for a specified display.

### Command Syntax

```bash
set_brightness [display_name] [brightness]
```

## Examples 
### List output displays :
```
$ set-brightness
Usage: ./set-brightness [display_name] [brightness]

Arguments:
  display_name: Name of the display (optional).
  brightness: New brightness level (optional, range: 0.0 - 1.0).

If no parameters are provided, this script shows the available displays.
If a display name is provided, it shows the current brightness.
If a display name and brightness are provided, it sets the new brightness level.

Available displays:
HDMI-1
```
### Read the current brightness
```
$ set-brightness HDMI-1
Current brightness of HDMI-1: 0.1 (Raw: 26 out of 255)
```
### Edit the current brightness
```
$ set-brightness HDMI-1 1
Brightness of HDMI-1 set to 255 (Scaled from 1).
```