# SQLcl (with optional JRE) Installer for Windows x64 - v25.1.1.113
Oracle does not provide a SQLcl installation package for Windows. This VS project will build an MSI for 64-bit Windows that will install SQLcl, an optional JRE, and update the system path.

## Disclaimers
This installer is not an official Oracle release, and the Oracle corporation is not involved in its development. I (@stchan) am not affiliated with Oracle in any way, have no involvement in the development of its products (including SQLcl), and do not represent it in any manner. SQLcl is the property of the Oracle corporation. Check your licensing agreement if you have concerns about building and/or using this installer.

## License
Any content that is not the property of Oracle (SQLcl and its associated material), and is the work of the author (@stchan) is MIT/X11 licensed.

## Tooling
* Visual Studio 2022

## Building
1. Download the latest SQLcl zip file from [here](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/download/).
1. Extract the "sqlcl" folder in the archive under the solution folder (ie. at the same level as the "sqlclinstaller" project folder). You can overwrite an empty existing "sqlcl" folder - .gitignore has an entry for that folder. If there are files in the folder (ie. an upgrade situation), I recommend emptying, or deleting it first, as the harvest process will gather everything. Any old/obsolete files would be included.
1. Download the latest 21 LTS Java JRE for Windows x64 zip file from [here](https://adoptium.net/temurin/releases/?os=windows&arch=x64&version=21&package=jre). You can substitue a JRE from another source if you prefer.
1. Extract the contents of the "jdk-21.x.x+x-jre" folder into the "jre" folder under the solution folder (ie. at the same level as the "sqlclinstaller" project folder). You can overwrite an empty existing "jre" folder - .gitignore has an entry for it. If there are files in the folder (ie. an upgrade situation), I recommend emptying, or deleting it first, as the harvest process will gather everything. Any old/obsolete files would be included.
1. Run the **buildrelease.ps1** script. Powershell 7.2 (or newer) is required.
1. The MSI will be in "publish\unsigned\\<culture>".

