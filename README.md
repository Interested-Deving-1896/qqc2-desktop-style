[update-readmes]   Mode: rewrite — migrating to template structure...
# qqc2-desktop-style

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/qqc2-desktop-style)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/qqc2-desktop-style.git
cd qqc2-desktop-style
```

## Usage


The name of the style is `org.kde.desktop`. 

On Plasma, this style is picked up automatically without the need to set an environment variable as long as both [Breeze](https://invent.kde.org/plasma/breeze) and [Plasma Integration](https://invent.kde.org/plasma/plasma-integration) are installed.

To support non-Plasma environments like Windows or GNOME, applications will need to define this style in code like [any other QQC style](https://doc.qt.io/qt-6/qtquickcontrols2-styles.html#using-styles-in-qt-quick-controls), e.g.:

```c++
#include <QQuickStyle>

int main(int argc, char *argv[])
{
    QApplication app(argc, argv);

    // Default to org.kde.desktop style unless the user forces another style
    if (qEnvironmentVariableIsEmpty("QT_QUICK_CONTROLS_STYLE")) {
        QQuickStyle::setStyle(QStringLiteral("org.kde.desktop"));
    }

    QQmlApplicationEngine engine;
    ...
}
```

**NOTE: the application must be a QApplication rather than a QGuiApplication instance in order for this style to be used.**

If the application supports Android, check if  `Q_OS_ANDROID` is defined first:

```c++
#ifdef Q_OS_ANDROID
    QGuiApplication app(argc, argv);
    // Set your preferred Android QQC style here, in this case QQC2 Breeze Style
    QQuickStyle::setStyle(QStringLiteral("org.kde.breeze"));
#else
    QApplication app(argc, argv);
    if (qEnvironmentVariableIsEmpty("QT_QUICK_CONTROLS_STYLE")) {
        QQuickStyle::setStyle(QStringLiteral("org.kde.desktop"));
    }
#endif
```

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/qqc2-desktop-style`](https://github.com/Interested-Deving-1896/qqc2-desktop-style) and mirrored through:

```
Interested-Deving-1896/qqc2-desktop-style  ──►  OpenOS-Project-OSP/qqc2-desktop-style  ──►  OpenOS-Project-Ecosystem-OOC/qqc2-desktop-style
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
