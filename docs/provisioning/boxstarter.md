# Boxstarter

## What is Boxstarter?

[Boxstarter](https://boxstarter.org/) provides a way to programmatically set-up Windows environments. This allows systems to be set-up by provisioning tools,
and yields reproducible machine states.

## Installing Boxstarter

Assuming Chocolately is installed, Boxstarter can be installed from an Admin
Powershell instance with the following:

```shell
choco install boxstarter
```
The `boxstarter` package is a meta-package that will install the following components.
  * boxstarter.bootstrapper
  * boxstarter.winconfig
  * boxstarter
  * boxstarter.chocolatey
  * boxstarter.common
