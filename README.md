# Ammo Patcher
A simple SKSE plugin to patch All AMMO at runtime. Supports All Runtimes.

- [NG](https://www.nexusmods.com/skyrimspecialedition/mods/109061/)

## Requirements

- [Git](https://git-scm.com/)
  - Download latest version from [Here](https://git-scm.com/downloads)
- [Visual Studio Community 2022](https://visualstudio.microsoft.com/)
  - Desktop development with C++
  
## User Requirements
- [Skyrim Script Extender](https://skse.silverlock.org/)
  - Needed For any SKSE Plugin
- [Address Library for SKSE](https://www.nexusmods.com/skyrimspecialedition/mods/32444)
  - Needed for SSE/AE
- [VR Address Library for SKSEVR](https://www.nexusmods.com/skyrimspecialedition/mods/58101)
  - Needed for VR

## Installation Instructions
Use Git GUI or At the Directory of your choice, open terminal (or) cmd (or) Powershell and enter
```
git clone https://github.com/JudahJL/Ammo-Patcher.git
```

## Extra
- It is Adviced to add "VsDevCmd.bat" from Visual Studio to your Terminal (or) IDE to execute automatically to avoid cmake errors like the one mentioned below.This was a HUGE Headache for me. If you want to know more about "VsDevCmd.bat", Google is your Friend.
```
  The CMAKE_CXX_COMPILER:

    cl.exe

  is not a full path and was not found in the PATH.
``` 
### Upgrading Packages (Optional)
If you want to upgrade the project's dependencies, run the following commands:
```bat
xmake repo --update
xmake require --upgrade
```

### Rules
```
Whitelist(ID) > Blacklist(ID) > Whitelist(File) > Blacklist(File)
```
## License

[MIT](LICENSE)

---

## Unofficial Skyrim 1.7.104 compatibility branch

This fork's `skyrim-1.7.104` branch is an **unofficial compatibility port** of Ammo Patcher, originally created by **JudahJL**. The build was tested locally with SkyrimSE.exe 1.7.104.0 and SKSE64 2.3.1, including SKSE Menu Framework integration and infinite ammo.

**Known issue:** In-game settings changed through SKSE Menu Framework sometimes do not apply immediately or consistently. Restarting Skyrim and applying the settings again helped in local testing, but this behavior has not been fully diagnosed. Compatibility with other installations is not guaranteed.

**Transparency:** AI assistance was used to adapt and recompile the source and to work on Address Library / CommonLibSSE-NG compatibility. The resulting DLL was tested by the fork maintainer in-game. Credit for the original mod remains with [JudahJL](https://github.com/JudahJL/Ammo-Patcher).

See [PORT_1.7.104.md](PORT_1.7.104.md) for technical details, test scope and build caveats.
