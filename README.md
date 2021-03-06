# docker-ci

Collection of docker images we use to build .NET libraries, services and
applications.

The images can be be run directly or be used as base images for custom build
environments (see notes below).

1. [lykkeoss/dotnet-core-lts-sdks](dotnet-core-lts-sdks) - Image containing the LTS
   versions of .NET Core SDKs (3.1.x, 2.1.x), git and docker-cli . Primarily used to
   build .NET libraries, services and applications.

2. [lykkeoss/dotnet-core-node](dotnet-core-node) - Image based on `dotnet-core-lts-sdks`
   above with addition of Node LTS. Primarily used to build applications with .NET
   backend(s) and JavaScript SPA frontend(s).

## lykkeoss/dotnet-core-lts-sdks

| Tag | OS Version / Arch | Contents | Dockerfile | CLI |
| - | - | - | - | - |
| 1 | Alpine 3.11 / x64 | .NET Core SDK 3.1.200, .NET Core SDK 2.1.805. git 2.24.3, docker-cli 19.03.5 | [dockerfile](dotnet-core-lts-sdks/1/dockerfile) | `docker pull lykkeoss/dotnet-core-lts-sdks:1` |
| 2 | Alpine 3.11 / x64 | .NET Core SDK 3.1.300, .NET Core SDK 2.1.806. git 2.24.3, docker-cli 19.03.5 | [dockerfile](dotnet-core-lts-sdks/2/dockerfile) | `docker pull lykkeoss/dotnet-core-lts-sdks:2` |

[View on DockerHub](https://hub.docker.com/repository/docker/lykkeoss/dotnet-core-lts-sdks)

## lykkeoss/dotnet-core-node

| Tag | OS Version / Arch | Contents | Dockerfile | CLI |
| - | - | - | - | - |
| 1 | Alpine 3.11 / x64 | Based on lykkeoss/dotnet-core-lts-sdks:1, node 12.15.0, npm 6.13.4  | [dockerfile](dotnet-core-node/1/dockerfile) | `docker pull lykkeoss/dotnet-core-node:1` |
| 2 | Alpine 3.11 / x64 | Based on lykkeoss/dotnet-core-lts-sdks:2, node 12.15.0, npm 6.13.4  | [dockerfile](dotnet-core-node/2/dockerfile) | `docker pull lykkeoss/dotnet-core-node:2` |

[View on DockerHub](https://hub.docker.com/repository/docker/lykkeoss/dotnet-core-node)

## Notes

- Images based on LTS version of software will, in general, be updated on a quarterly basis or
  if a particular urgent fix is required.
- It is not intended to support all possible version combinations.
- PRs to bump versions welcome. PRs must include Tag docs.
