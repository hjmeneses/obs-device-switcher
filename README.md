# Device Switcher plugin for OBS Studio

> **About this fork**
>
> This is a fork of [exeldro/obs-device-switcher](https://github.com/exeldro/obs-device-switcher). All credit
> for the plugin goes to Exeldro; the original README follows unchanged below this note.
>
> **Why it exists:** the original no longer loads in OBS Studio 33, which removed `obs_frontend_add_dock`.
> The [`obs33-port`](https://github.com/hjmeneses/obs-device-switcher/tree/obs33-port) branch ports it:
>
> - Builds with the current [obs-plugintemplate](https://github.com/obsproject/obs-plugintemplate) against
>   OBS 33 and Qt 6 on Windows, macOS and Ubuntu (sources moved to `src/`). The in-tree build steps below
>   are from the original and no longer apply to this branch.
> - The dock is registered with `obs_frontend_add_dock_by_id`, keeping the `DeviceSwitcherDock` id so saved
>   dock layouts still apply.
> - Deprecated APIs replaced (audio monitoring, autoselect values, `QCheckBox::stateChanged`).
> - Fixes: a null `config_set_string` call without a profile config, source settings not released after
>   reading, and the `source_save` signal not disconnected on destruction.
>
> The `master` branch tracks upstream without changes.

Plugin for OBS Studio to add a device switcher dock.

# Build
1. In-tree build
    - Build OBS Studio: https://obsproject.com/wiki/Install-Instructions
    - Check out this repository to UI/frontend-plugins/device-switcher
    - Add `add_subdirectory(device-switcher)` to UI/frontend-plugins/CMakeLists.txt
    - Rebuild OBS Studio

1. Stand-alone build (Linux only)
    - Verify that you have package with development files for OBS
    - Check out this repository and run `cmake -S . -B build -DBUILD_OUT_OF_TREE=On && cmake --build build`

# Donations
https://www.paypal.me/exeldro

Thanks to the contributions of [EF Education First](https://ef.com)
