# PySide BaseApp
This Flatpak base app is specifically designed for packaging Flatpak applications that utilize PySide, the official Python bindings for the Qt framework.

*If you would like to contribute to the enhancement of this documentation, please feel free to open a pull request against the wiki branch on the [GitHub repository](https://github.com/pyside/io.qt.PySide.BaseApp/tree/wiki).*

## PySide6 modules included

All PySide6 modules are available with this base app, except for the following:
- Qt6Quick3D
- Qt6SerialBus
- Qt6DataVisualization
- Qt6Graphs
- Qt6HttpServer

> **Note:**  The above-mentioned modules are missing because they are not available with the Kde runtime nor the [Web Engine base app](https://github.com/flathub/io.qt.qtwebengine.BaseApp/tree/wiki).

## Branches Supported

| Branch     | Maintained |
|------------|------------|
| 6.7        | Yes        |
| 6.8        | Yes        |

> **Note:** Each branch represents the latest patch release for that branch version. When the Kde runtime updates the Qt patch version, the branch of PySide6 should also be updated
in the manifest file.

## Cleanup

Please make sure to clean up development files from the BaseApp, in the application

```yaml
cleanup-commands:
  - /app/cleanup-BaseApp.sh
```

> **Note:** This requirement comes from the [Web Engine base app](https://github.com/flathub/io.qt.qtwebengine.BaseApp/tree/wiki). This script also
removes some unnecessary PySide6 binaries.

## Usage

```yaml
id: <your.pyside.app.id>
runtime: org.kde.Platform
runtime-version: '6.8'
sdk: org.kde.Sdk
base: io.qt.PySide.BaseApp
base-version: '6.8'
cleanup-commands:
  - /app/cleanup-BaseApp.sh
modules:
  - name: <Your PySide App>
...
```