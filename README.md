Forked from https://github.com/BaerMitUmlaut/A3G-SpectatorCam to add compability with the [A3G Framework Modules](https://github.com/a3g/a3g-framework-modules).

# A3G Spectator Cam
A simple spectator cam script made for AGM users. Compatible with ACRE and TFAR.

## Installation
Download script and put it inside `modules\a3g-spectator-cam`. To activate the camera when the player gets killed just copy the following lines of code into your Description.ext:

```c++
respawnTemplates[] = {"A3G_SpectatorCam"};

class CfgRespawnTemplates {
  #include "modules\a3g-spectator-cam\cfgRespawnTemplates.hpp"
};
class RscTitles {
  #include "modules\a3g-spectator-cam\rscTitles.hpp"
};
class CfgFunctions {
  #include "modules\a3g-spectator-cam\cfgFunctions.hpp"
};
```

Make sure you don't have any duplicate settings in your Description.ext.

## Usage
Ideally you're using the script with the `BASE` [respawn type](https://community.bistudio.com/wiki/Arma_3_Respawn#Respawn_Types). This is because the `BASE` respawn type does not consume slots if people leave and come back to your mission. The script is compatible with respawn. You can set `respawnDelay` to any value you want, setting it to a really really high value with `BASE` respawn type essentially disables respawn, while keeping the other benefits.

You can also execute the camera during the mission by using `[player] spawn A3G_SpectatorCam_fnc_InitCam`, just be aware that there is right now no way to exit the spectator camera, so you will be stuck in the camera until you respawn.

## Controls
Keybind | Usage
------- | -----
H | Show/Hide help
WASD | General movement
QE | Vertical movement
Shift | Faster movement
Alt | Slower movement
N | Default vision/night vision/thermal vision
Space | Free cam/3rd person/1st person - aim at unit to spectate
Arrow left/right | Switch to previous/next player

## Requirements
This camera was intended to be used with AGM, however it should also work without AGM. Nothing else is required.
