---
title: Setup Guide
---

## Required Software

- [BizHawk from TASVideos](https://tasvideos.org/BizHawk/ReleaseHistory){:target="_blank"}
  - Be sure to read the [Installing section of the README](https://github.com/TASEmulators/BizHawk#installing){:target="_blank"} for full installation instructions
- Archipelago BizHawk Client
  - This is part of [Archipelago](https://github.com/ArchipelagoMW/Archipelago/releases){:target="_blank"} itself
- A valid Tails Adventure ROM file legally obtained from either:
  - A genuine Tails Adventure Game Gear cartridge, or
  - An official re-release e.g. Sonic Adventure DX, Sonic Gems Collection, or Sonic Origins

## Configuring BizHawk

After installing BizHawk, open EmuHawk and change the following settings:

1. Go to Config > Customize, and enable "Run in background"
  - This will prevent disconnecting from the client while running in the background
1. **Version 2.8 or earlier:** Go to Config > Customize, then the Advaned tab, switch the Lua Core from `NLua+KopiLua` to `Lua+LuaInterface`, then restart EmuHawk
  - **Note:** Even if `Lua+LuaInterface` is already selected, change the option to something else then back again to ensure the correct Lua Core is loaded

On Windows, it's strongly recommended to associate Game Gear ROMs (*.gg) with EmuHawk:
1. Find any Game Gear ROM you own
1. Right-click the ROM and select 'Open With...'
1. Ensure 'Always use this app to open .gg files' is checked
1. Select 'Look for another application'
1. Find and select the EmuHawk.exe installed from the above

## Configuring game options

Game options are configured using a YAML file that the player submits (either solo or in a bundle) to generate a multiworld.

### What is a YAML file?

Your YAML file defines all the necessary options that are used when generating a multiworld. Each (copy of a) game has its own YAML file tailored to the specific needs and desires of the player of each (copy of a) game.

### Where can I get a YAML file?

1. Open `ArchipelagoLauncher.exe`
1. Click `Open` on `Generate Template Options`
    - A folder window will open with a template for every bundled and installed APWorld
1. Locate the `Tails Adventure.yaml` and copy it to a convenient location
1. Open the copied `Tails Adventure.yaml` in a suitable text editor and set your options
    - It's recommended to use a text editor with YAML syntax highlighting support e.g.
        - Visual Studio Code with the YAML extension from Red Hat
        - Notepad++

## Joining a MultiWorld Game

### Generating and Patching a Game

1. Create your YAML options file
1. Follow the instructions in the [Generating a Game](../../Archipelago/setup/en#generating-a-game) section of the Archipelago setup guide
  - This will generate a patch file with an `.aptailsadv` extension inside the generated zip archive
1. Open `ArchipelagoLauncher.exe`
1. Select `Open Patch` and locate your patch file from step 2
  - If this is the first time launching the game, you will also be prompted to locate your original ROM
1. A patched `.gg` file will be created in the same place as your patch file
1. The BizHawk Client will be automatically started along with the BizHawk emulator
  - If this is your first time opening a patch with the BizHawk Client, you will be asked to locate `EmuHawk.exe`

Due to progression being saved server-side, it is not possible to play a solo world without connecting to a server.

### Connect to the Multiserver

Normally, steps 1-5 will be performed automatically. However, it's good to be familiar with how to perform these steps in case you need to do it manually.

1. Open the BizHawk Client
1. Run EmuHawk and load your patched ROM
1. In EmuHawk, go to 'Tools > Lua Console'
  - The Lua Console must remain open while playing
1. In the Lua Console window, go to 'Script > Open Script...'
1. Navigate to your Archipelago install folder and open `data/lua/connector_bizhawk_generic.lua`
  - Alternatively, the Lua file can be drag-and-dropped on the Lua Console window
1. The emulator may stutter as the connection to the BizHawk Client is established - this is normal and will stop once the connection is established
1. Connect the BizHawk client to the server:
  1. Enter your room's address and port e.g. `archipelago.gg:38281` into the top text box
  1. Check the slot name and password are correct (if not using a password, use `None`)
  1. Click 'Connect'

For best results, connect when the game is either at the title screen or playing the intro sequence.

Once everything is correctly connected and running, there's only one thing left to do: _get gaming!_