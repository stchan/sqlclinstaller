# SQLcl (with optional JRE) Installer for Windows
Oracle does not provide a SQLcl installation package for Windows. This VS project will build an MSI that will install SQLcl, an optional JRE, and update the system path.

## Disclaimers
This installer is not an official Oracle release, and the Oracle corporation is not involved in its development. I (@stchan) am not affiliated with Oracle in any way, have no involvement in the development of its products (including SQLcl), and do not represent it in any manner. SQLcl is the property of the Oracle corporation. Check your licensing agreement if you have concerns about building and/or using this installer.

## License
Any content that is not the property of Oracle (SQLcl and its associated material), and is the work of the author (@stchan) is MIT/X11 licensed.

## Tooling
* Visual Studio 2026 (or later) with the [Heatwave](https://marketplace.visualstudio.com/items?itemName=FireGiant.FireGiantHeatWaveDev17) extension.

## Building
1. Download the latest **SQLcl zip** file from [here](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/download/).
1. Extract the "**sqlcl**" folder in the archive under the solution folder (ie. at the same level as the "**sqlclinstaller**" project folder). You can overwrite an empty existing "sqlcl" folder - .gitignore has an entry for that folder. If there are files in the folder (ie. an upgrade situation), I recommend emptying, or deleting it first, as the harvest process will gather everything. Any old/obsolete files would be included.
1. Download the latest Java 21 LTS JRE for Windows zip file from [here](https://adoptium.net/temurin/releases/?os=windows&arch=any&version=21&package=jre). You can substitute a JRE from another source if you prefer.
1. Extract the contents of the "**jdk-21.x.x+x-jre**" folder into the "java\\\<cpuarch>\jre" folder (ex. "**java\x64\jre**" for **x64**) under the solution folder (ie. at the same level as the "sqlclinstaller" project folder). If there are files in the folder (ie. an upgrade situation), emptying, or deleting it is recommended, as the harvest process will gather everything. Any old/obsolete files would be included.
1. Update \<ProductVersion\> in the **directory.build.props** file if necessary.
1. Run the **publishrelease.ps1** script. Powershell 7.2 (or newer) is required.
1. The MSI will be in "publish\unsigned\\\<culture>" (ex. "**publish\unsigned\en-us**" for American English).

