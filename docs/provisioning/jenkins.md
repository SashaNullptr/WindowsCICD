# Jenkins

## What is Jenkins?
[Jenkins](https://jenkins.io/) is the _de facto_ standard free and open source CI/CD system. It is generally more hands-on to set up compared to commercial tools like Travis-CI, but it is extremely flexible and adaptable.

## Installation

We will be running Jenkins as a Docker image, and thus installation will be through Docker.

Note we will assume the target system is equipped with the Chocolately package manager.

### Install Docker

First we will need to install docker itself. Fortunately this is a simple matter running the following commands in PowerShell:

```shell
C:\> choco install docker-toolbox
```

To verify Docker installed successfully run

```shell
C:\> docker run hello-world
```

To install Jenkins itself we will run the following command in a command prompt.

```shell
docker run ^
  --rm ^
  -u root ^
  -p 8080:8080 ^
  -v jenkins-data:/var/jenkins_home ^
  -v /var/run/docker.sock:/var/run/docker.sock ^
  -v "%HOMEPATH%":/home ^
  jenkinsci/blueocean
```
