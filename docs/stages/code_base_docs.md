# Code Base Documentation

Automatic code base documentation is a critical part of making

## Documentation Tools

## C&#35;

### DocFX

[DocFX](https://dotnet.github.io/docfx/) is one of the few .NET documentation tools that allows
docs to be built programmatically in a fairly sane way. It also allows auto-generated
content to be mixed with hand-written documentation. In many ways it feels like
the .NET analog to the wonderful Python documentation generator [Sphinx](http://www.sphinx-doc.org/en/master/).

#### Configuration

DocFX relies on a main config file called `docfx.json` that contains most of the
information about how the docs should be built, along with `toc.yml` files
that define how a sub-module is structured.

A minimal `docfx.json` and `toc.yml` that extracts all XML comments from a C&#35; project and
automatically generates documentation for each commented piece of code is shown
below.

`doxfx.json`
```json
{
  "metadata": [
    {
      "src": [
        {
          "files": [
            "practice_app/**.csproj"
          ]
        }
      ],
      "dest": "api",
      "disableGitFeatures": false,
      "disableDefaultFilter": false
    }
  ],
  "build": {
    "content": [
      {
        "files": [
          "api/**.yml",
          "api/index.md"
        ]
      },
      {
        "files": [
          "toc.yml",
          "*.md"
        ]
      }
    ],
    "resource": [
      {
        "files": []
      }
    ],
    "overwrite": [
      {
        "files": [],
        "exclude": [
          "obj/**",
          "_site/**"
        ]
      }
    ],
    "dest": "_site",
    "globalMetadataFiles": [],
    "fileMetadataFiles": [],
    "template": [
      "default"
    ],
    "postProcessors": [],
    "markdownEngineName": "markdig",
    "noLangKeyword": false,
    "keepFileLink": false,
    "cleanupCacheHistory": false,
    "disableGitFeatures": false
  }
}
```

`toc.yml`
```yml
- name: Code Base Documentation
  href: api/
```

This config file will have DoxFX extract all comments from an app named `pratice_app`
and generate YML and MarkDown files and place them in a directory named `api`.
The generated files in `api` will then be used to make the final HTML docs, which
will be placed in `_site`.

#### Building

A minimal script that will install DocFX and then use it to build documentation
(suitable for CI/CD use) is shown below.

```shell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
refreshenv
choco install docfx -y
docfx docfx.json
```
