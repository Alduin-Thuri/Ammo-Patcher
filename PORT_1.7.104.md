# Ammo Patcher 3.0.1 — Skyrim 1.7.104 compatibility port

> **Unofficial, community-maintained compatibility port.** Original Ammo Patcher by [JudahJL](https://github.com/JudahJL/Ammo-Patcher). This fork is not an official update from the original author.

## Target environment

- SkyrimSE.exe **1.7.104.0**
- SKSE64 **2.3.1**
- Address Library database for **1.7.104.0** (v13 / format 5)
- CommonLibSSE-NG, with local compatibility adjustments used during development
- SKSE Menu Framework, for the optional in-game preset editor

## What was changed

- Rebuilt the plugin as **Ammo Patcher 3.0.1** for the target Skyrim runtime.
- Adapted the build and Address Library / CommonLibSSE-NG integration for the 1.7.104 environment.
- **Restored SKSE Menu Framework integration**, including the **Edit Presets** interface. `UI.cpp` and the ImGui helper translation units are included in the working build.
- Adjusted the SKSE Menu Framework header integration to resolve the framework module when needed rather than relying on a one-time early lookup.
- Retained the original JSON presets, ammo/projectile patching, rules, logging and infinite-ammo functionality.

## Testing and known limitations

I built and tested this version on **my own Skyrim 1.7.104 setup**. The DLL loaded, ammo records were patched, the SKSE Menu Framework menu opened, and infinite ammo worked in my testing.

**Known intermittent behavior:** Changes made through SKSE Menu Framework do **not always take effect on the first attempt**. Sometimes they apply correctly; other times they appear not to persist or activate immediately. In my testing, restarting Skyrim and adjusting the settings again helped. The underlying cause has **not** been confirmed or fixed.

This is a **personal compatibility port**, not a guarantee that every option works reliably on every installation. Other Skyrim runtimes and mod combinations have not been validated by me. Please back up your configuration and report reproducible issues with logs and steps to reproduce.

## AI assistance and credits

I used **AI assistance** to help reassemble, modify and recompile the source, including work related to Address Library / CommonLibSSE-NG compatibility and SKSE Menu Framework integration. I then **tested the resulting build myself in-game**. I am not claiming to have authored the original plugin or to have independently verified every code path.

**Original project and credit:** [JudahJL / Ammo-Patcher](https://github.com/JudahJL/Ammo-Patcher). Please retain the original copyright notices and license.

## Building from source

The build uses **xmake** and a Windows/MSVC C++ toolchain. In the configured source tree, run:

```powershell
xmake -r
```

The resulting DLL is placed in `build/windows/x64/release/Ammo_Patcher.dll` and, in the tested project configuration, copied to `contrib/Distribution/data/skse/plugins/Ammo_Patcher.dll`.

**Important:** The working build also relied on local CommonLibSSE-NG / Address Library compatibility changes. Simply downloading an unmodified CommonLibSSE-NG release may **not** reproduce this build. Verify that the required dependency changes are included or documented before treating this repository as fully reproducible from a fresh clone.

## Applying the CommonLibSSE-NG compatibility patch

After cloning the repository and initializing its submodules,
apply the included patch from the project root:

```powershell
git -C lib/commonlibsse-ng apply ../../CommonLibSSE-NG_1.7.104.patch
