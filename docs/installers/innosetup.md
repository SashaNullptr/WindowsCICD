# InnoSetup

## What is InnoSetup?

[InnoSetup](http://www.jrsoftware.org/isinfo.php) is one of the most widely used packages
for generating self-contained Windows installers, although not quite as popular
as the [Nullsoft Scriptable Installer](https://nsis.sourceforge.io/Main_Page).

## Installation

Innosetup is available via Chocolatey and can be installed with the following command.

```shell
choco install innosetup
```

## Programmatic Use of InnoSetup Installers

Fortunately InnoSetup installers can also be programmatically installed without
any additional tooling.

Any InnoSetup installer can be run from the command line using `setup.exe /$option0
/$option1 ...`.
While there are [quite a few options available](http://www.jrsoftware.org/ishelp/index.php?topic=setupcmdline) we will focus on the ones relevant to surpressing the
GUI.

| Option | Effect |
|--------|--------|
| `/silent` | Only display the progress bar |
| `/verysilent` | Suppress _all_ GUI elements. |
| `/suppressmsgboxes` |Suppress message boxes (must be combined with silent or verysilent options) |
| `/nocancel` | Install process cannot be canceled |
| `/norestart` | Do not restart, even if doing so is required for the installation to take effect |
| `/dir="C:\$DIR_NAME"`| Override default install directory |

In general, the following command will be suitable for installing InnoSetup installers
in headless environments.

```shell
setup.exe /verysilent /suppressmsboxes /norestart
```
