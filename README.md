# eM Client for Linux

Information on how to get eM Client running on Linux using WINE with license activation, fonts and file associations working.

## Installation with Lutris

Install [Lutris](https://lutris.net/downloads)
Run `lutris -i https://raw.githubusercontent.com/BenJamesAndo/Linux-eMClient/refs/heads/main/em-client-lutris-installer.yaml`

If installed via Flatpak run `flatpak run net.lutris.Lutris -i https://raw.githubusercontent.com/BenJamesAndo/Linux-eMClient/refs/heads/main/em-client-lutris-installer.yaml`

## Installation with Bottles

Install https://usebottles.com

Then download https://github.com/Open-Wine-Components/umu-proton

Put umu-proton into Bottles runner, e.g. `/home/user/.local/share/bottles/runners/UMU-Proton-9.0-4e`
Using [ProtonPlus](https://protonplus.vysp3r.com/) can help you find your runners location for Bottles

Next download Segoe fonts for Linux
https://github.com/mrbvrz/segoe-ui-linux

Now create a new Bottle. Pick UMU-Proton-9.0-4e

After creation under Settings set Windows Version to Windows 8.1

Then open Registry Editor and import `regedit-import.reg`
To find them when importing place them in your Documents folder.

Paste in the Segoe Fonts into the Bottles font folder e.g. `/home/user/.local/share/bottles/bottles/eMClient/drive_c/windows/Fonts`

Under Dependencies install allfonts

Download eMClient for Windows: https://www.emclient.com/dist/latest/setup.msi

In eMClient bottle install setup.msi

Run eMClient and enjoy!

Please note eM Client doesn't officially support Linux. You can vote for support at https://emclient.sleekplan.app/feedback/150695
