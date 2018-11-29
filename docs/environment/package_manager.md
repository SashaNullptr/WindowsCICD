# Package Manager

Windows generally favors GUI installers, which presents a fairly severe problem
for CI/CD systems. In order to (somewhat) assuage this issue we will make use of
a package manager--this will allow us to install and update packages
programmatically.

## Chocolatey

We will be using the _de facto_ standard package manager for Windows--[Chocolatey](https://chocolatey.org/).

### Installation

Of course we also need a programmatic way to install Chocolatey itself. Fortunately we can do this pretty easily using the following PowerShell command.

```shell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

After the install script runs, it is generally a good idea to make sure Chocolately is up to date.

```shell
choco upgrade chocolatey
```
