# eM Client for Linux

eM Client can be run on Linux using Wine. This project provides a Lutris installer that handles prefix configuration, font setup, and Wine registry tweaks automatically. A manual Bottles install guide is also included below.

eM Client does not officially support Linux. You can vote for official support at [emclient.sleekplan.app](https://emclient.sleekplan.app/feedback/150695).

## Lutris Installation

### Requirements

- [Lutris](https://lutris.net/downloads)
- A working Wine runner (see Troubleshooting below if the install fails)

### Install

Run the following command to launch the installer:

```sh
lutris -i https://raw.githubusercontent.com/BenJamesAndo/Linux-eMClient/refs/heads/main/em-client-lutris-installer.yaml
```

If Lutris is installed as a Flatpak:

```sh
flatpak run net.lutris.Lutris -i https://raw.githubusercontent.com/BenJamesAndo/Linux-eMClient/refs/heads/main/em-client-lutris-installer.yaml
```

### What the installer does

- Optionally downloads the [UMU-Proton-9.0-4e](https://github.com/Open-Wine-Components/umu-proton/releases/tag/UMU-Proton-9.0-4e) runner into your Lutris runners directory
- Creates a 64-bit Wine prefix configured for Windows 8.1
- Installs core fonts and the full [Segoe UI font family](https://github.com/mrbvrz/segoe-ui-linux)
- Configures file associations so email attachments open natively on Linux
- Downloads and runs the latest eM Client installer

### After installation

Set the Wine runner to UMU-Proton-9.0-4e for best compatibility:

1. Right-click eM Client in Lutris and select Configure
2. Go to Runner options
3. Set Wine version to `UMU-Proton-9.0-4e`
4. Click Save

### Troubleshooting

**The installer fails with a GE-Proton traceback mentioning `protonfixes`**

To work around this:

1. Open Lutris and go to Preferences > Runners > Wine
2. Set the default Wine version to System Wine
3. Re-run the installer

---

## Bottles Installation

### Requirements

- [Bottles](https://usebottles.com)
- [UMU-Proton-9.0-4e](https://github.com/Open-Wine-Components/umu-proton/releases/tag/UMU-Proton-9.0-4e) runner
- [Segoe UI fonts for Linux](https://github.com/mrbvrz/segoe-ui-linux)
- [ProtonPlus](https://protonplus.vysp3r.com/) (optional, useful for locating the runners directory)

### Steps

1. Place the UMU-Proton runner in the Bottles runners directory, for example:
   `~/.local/share/bottles/runners/UMU-Proton-9.0-4e`

2. Create a new Bottle and select UMU-Proton-9.0-4e as the runner.

3. Under Settings, set Windows Version to Windows 8.1.

4. Open the Registry Editor and import `regedit-import.reg`.
   Place the file in your Documents folder to find it easily when browsing for it.

5. Copy the Segoe UI fonts into the prefix font directory, for example:
   `~/.local/share/bottles/bottles/eMClient/drive_c/windows/Fonts`

6. Under Dependencies, install `allfonts`.

7. Download the eM Client installer from https://www.emclient.com/dist/latest/setup.msi and install it inside the bottle.

## Screenshot

<img width="1917" height="1080" alt="eM_Client_SS" src="https://github.com/user-attachments/assets/e541b4c4-550f-4384-881b-9a16bdbc8bf2" />
