# GSConnect Android Files Launcher

A workaround for GSConnect devices where the SFTP mount opens at the inaccessible filesystem root (`/`) instead of the Android shared storage location (e.g. `/storage/emulated/0`).

The script:

- Detects connected and paired GSConnect devices.
- Supports multiple devices with an optional device chooser.
- Uses GSConnect's native SFTP mount function.
- Automatically detects common Android storage locations.
- Supports per-device storage path overrides.
- Opens the accessible storage directly in the default file manager.
- Obtains network and connection details dynamically from GSConnect.

## Requirements

Install GSConnect, Nautilus integration and Zenity, if using Fedora, use:

    sudo dnf install gnome-shell-extension-gsconnect nautilus-gsconnect zenity

## Installation

Copy `android-files` to:

    ~/.local/bin/android-files

Make it executable:

    chmod +x ~/.local/bin/android-files

To add **Android Files** to the GNOME application menu, create:

    ~/.local/share/applications/android-files.desktop

With the following contents:

    [Desktop Entry]
    Type=Application
    Name=Android Files
    Comment=Browse Android storage via GSConnect
    Exec=/home/USERNAME/.local/bin/android-files
    Icon=phone
    Terminal=false
    Categories=Utility;FileManager;

Replace `USERNAME` with your Linux username, then run:

    chmod +x ~/.local/share/applications/android-files.desktop
    update-desktop-database ~/.local/share/applications

The launcher can then be opened from the GNOME application menu or pinned to the dock.

## Configuration

Configuration options are located near the top of the script.

The script tests several common Android storage paths automatically. Device-specific paths can also be configured using `DEVICE_PATH_OVERRIDES`.

## License

Released under the MIT License.
