# Beat Saber HTTP Status

This plugin exposes information about the current game status, live over a WebSocket and over HTTP. It can be used to build [custom stream overlays](https://github.com/opl-/beatsaber-http-status/wiki/Software-using-this-plugin#overlays) or track player performance by third party programs.


## Installation

### Recommended (ModSaber Installer)

To install Beat Saber HTTP Status use [ModSaber Installer](https://github.com/lolPants/modsaber-installer/releases) where it's listed as "HTTP Status". This will automatically install all required plugins and keep all of them up to date.

Next you will need to [get additional software](https://github.com/opl-/beatsaber-http-status/wiki/Software-using-this-plugin) that uses this plugin. **This plugin does nothing useful on its own; it simply exposes information for other programs to use.**

### Manual

1. Download the latest release from the [releases page](https://github.com/opl-/beatsaber-http-status/releases).

2. Extract the zip into your Beat Saber directory.

3. Download and extract the following plugins and their dependencies:

	- https://www.modsaber.org/mod/bs-utils/

4. [Get additional software](https://github.com/opl-/beatsaber-http-status/wiki/Software-using-this-plugin) that makes use of this plugin. This mod does nothing on its own; it simply exposes information for other programs to use.


## Developers

### Using HTTP Status

Protocol documentation can be found in [protocol.md](protocol.md).

### Contributing to HTTP Status

This project uses the `websocket-sharp` library included as a git submodule. To download it, use `git submodule update --init` or clone the repository with the `--recursive` flag.

To build this project you will need to create a `BeatSaberHTTPStatus/BeatSaberHTTPStatusPlugin.csproj.user` file specifying where the game is located on your disk:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <!-- Change this path if necessary. Make sure it ends with a backslash. -->
    <GameDirPath>C:\Program Files\Steam\steamapps\common\Beat Saber\</GameDirPath>
  </PropertyGroup>
</Project>
```

Alternatively you can provide the game DLLs in the `libs/beatsaber` directory using the standard Beat Saber directory structure. For a full list see the [project file](BeatSaberHTTPStatus/BeatSaberHTTPStatusPlugin.csproj).


## Credits

**xyonico** for the [Beat Saber Discord Presence](https://github.com/xyonico/BeatSaberDiscordPresence) plugin, on which this plugin was initially based.

**sta** for the [websocket-sharp](https://github.com/sta/websocket-sharp) library.

**Maxaxik** for testing and helping with research.
