# [Binaries for Edge.js](https://www.nuget.org/packages/Edge.js.Binaries/)

__`DllNotFoundException` when using [Edge.js](https://github.com/tjanczuk/edge)?__

__Want to use continuous delivery AND [Edge.js](https://github.com/tjanczuk/edge)?__

```
> Install-Package Edge.js.Binaries -Version 8.2.1
> dotnet add package Edge.js.Binaries --version 8.2.1
> paket add Edge.js.Binaries --version 8.2.1
```

[![NuGet](https://img.shields.io/nuget/v/Edge.js.Binaries.svg)](https://www.nuget.org/packages/Edge.js.Binaries/)
[![GitHub license](https://img.shields.io/github/license/TheInsaneBro/Edge.js.Binaries.svg)](https://github.com/TheInsaneBro/Edge.js.Binaries/blob/master/LICENSE)

With [Edge.js](https://github.com/tjanczuk/edge) you can script Node.js from C# and vice versa. When using a C# project to script Node.js you might have run into the trouble of a `DllNotFoundException` when not copying the `edge`-folder into the project root and build directory (does not happen automatically when using `.net.core` project templates). This is a tedius process and dificult to implement in a continuous delivery environment (without checking binaries into git).

[This NuGet package](https://www.nuget.org/packages/Edge.js.Binaries/) provides all native binaries and internal scripts needed to run Edge.js. This package copies the `edge`-folder to the build directory and creates a link in the project root to make debugging possible. The version of the packages `Edge.js.Binaries` and `Edge.js` will always match so there are no incompatibilites.

Demo
---

This is how an simple `.net-core` console project would look like after installing both `Edge.js` and `Edge.js.Binaries`. A link to the required binary files will pop up. These files are also copied into the build directory when building the project.

![Edge.js.Binaries Demo](https://i.imgur.com/AgI6qgl.png "Edge.js.Binaries Demo")

Without `Edge.js.Binaries` this code would end in an `DllNotFoundException`.

__Hint: Your project has to target one of Edge.js supported platforms the be functional, e.g. `net461`__
