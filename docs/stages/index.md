# Overview of Build Stages

We will organize our CI/CD stages in the following way.

| Stage | Description |
|-------|-------------|
| Image Build | Build Docker/VMs for each supported platform. |
| Unit Test | Build and run unit test harness. |
| Integration Tests | Test how project interacts with other programs / components. |
| Packaging | Bundle project into package. |
| Installation Tests | Check compiled package to see if it installs properly on target platforms. |
| Static Analysis | Run style checking, linting, and code coverage tests. |
| Documentation | Generate code base and project docs. |
| Pages | Host project documentation as static site. |
| Deploy | Post compiled packages to a known location for internal/customer use. |
