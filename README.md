<img height=auto width=29% src="https://raw.githubusercontent.com/cdev-tux/q3lite/master/misc/q3lite/img/q3lite_logo.gif" alt="Q3lite Logo"><img height=auto width=69% src="https://raw.githubusercontent.com/cdev-tux/q3lite/master/misc/q3lite/img/q3lite-screenshot.jpg" alt="Q3lite Screenshot">

&nbsp; &nbsp; **Q3lite** is an updated [id Tech 3](https://en.wikipedia.org/wiki/Id_Tech_3) game engine for embedded Linux systems.  The project is a fork of [ioquake3](https://github.com/ioquake/ioq3). Q3lite provides users with an updated version of the engine running on [OpenGL ES](https://www.khronos.org/opengles) and [SDL2](https://www.libsdl.org).  The goal of the project is to add useful new features that enhance the game experience for both players and server administrators while staying in sync with the updated Quake III Arena engine.  The long term plan is to slim the code down to improve performance on low-end embedded processors, hence the name Q3lite.


### Platforms

  * Raspberry Pi Zero, Zero W
  * Raspberry Pi 1 Model A+, B, B+ w/512 MB Memory
  * Raspberry Pi 2
  * Raspberry Pi 3, 3A+, 3B+
  * Pi platforms are supported on Raspbian Desktop and Raspbian Lite


### Features

<img src="https://raw.githubusercontent.com/cdev-tux/q3lite/master/misc/q3lite/img/app_menu.jpg" width="430" align="right" style="margin-left:8px;margin-top:5px" alt="App Menu">

  * Built on the latest ioq3 codebase using OpenGL ES.
  * Set the game resolution independent of your desktop resolution on the Pi.
  * Play full screen with or without x11 running.
  * Optimized player and dedicated server config files included with instructions for each setting.
  * The provided compile script automatically detects the Pi processor type and sets optimized compiler settings.
  * Includes a robust installer to automatically create game directories, copy game files and download&nbsp;/&nbsp;install updated pak files from the Q3A Point Release. It can also install SDL2 dynamic  libraries so there's no need to compile or preinstall SDL2. The installer creates game, server, rcon and   timedemo launch icons in the applications menu as seen in the image above.  
  **Note:** You'll still need to copy the pak0.pk3 file from your full version of Quake III Arena to play the game. See section 1.1 of the [Q3lite FAQ](https://github.com/cdev-tux/q3lite/wiki/Q3lite-FAQ) for details.
  * Uninstaller included for removing installation if desired.
  * Includes all files and step by step instructions to run a dedicated server from the applications menu or as a systemd service at boot time.
  * Timedemo four runs at ~150 fps on a Pi 3 B+ at 720P (without overclocking).
  * Also includes a desktop Remote Console (rcon) application to send console commands to the background server.

### New Q3lite cvars
These cvars are in addition to those currently available in the base game. All new features can be turned off to maintain default Quake3 behavior. Set client cvars in your autoexec.cfg file and server cvars in your server.cfg file, both located in ~/.q3a/baseq3.

```
Client cvars:

  cg_drawSpeedometer <0|1>          - Toggle display of player speed in
                                      Quake units per second.  Speed shown in
                                      upper right corner under the match clock.
                                      Also works with demos and while following
                                      other players in spectator mode.
                                      0 = disabled.
                                      1 = enabled.

  cg_nochatbeeps <0|1|2|3>          - Toggle playing of the chat beep sound.
                                      Handy on servers with chatty spectators.
                                      0 = disabled.
                                      1 = No chat beeps for non-team chat only.
                                      2 = No chat beeps for team chat only.
                                      3 = No chat beeps for team / non-team chat.

  cg_novotebeeps <0|1|2|3>          - Toggle playing of the vote beep sound.
                                      0 = disabled.
                                      1 = No vote beeps for non-team votes only.
                                      2 = No vote beeps for team votes only.
                                      3 = No vote beeps for team / non-team votes.

  cg_noTaunts <0|1>                 - Toggle playing of client taunt sounds.
                                      Useful when opponents press the taunt
                                      key excessively.
                                      0 = disabled.
                                      1 = No taunt sounds played.

Server cvars:

  g_intermissionDuration <seconds>  - Limits end-of-round intermission duration.
                                      Prevents endless intermission if a human
                                      player is away from the keyboard.
                                      0 = disabled.
                                      > 0 = intermission duration in seconds,
                                      then server moves to the next map.
                                      Valid range 5 - 30 seconds.

  sv_inactivity <seconds>           - Move player to spectator mode after a
                                      period of inactivity rather than kick them
                                      as g_inactivity does. Set to a lower value
                                      than g_inactivity if both are used.
                                      0 = disabled.
                                      > 0 = inactivity period in seconds, then
                                      server moves player to spectator mode.

  sv_maxconcurrent <0|1..64>        - Limits the number of simultaneous player
                                      connections from the same IP address.
                                      0 = disabled.
                                      Valid range 1 - 64.
```

### Getting Started

  * See the [Compiling and Installation Guide](https://github.com/cdev-tux/q3lite/wiki/Compiling-Install-Guide) for instructions on how to get Q3lite up and running.
  * Copy the pak0.pk3 file from your official copy of Quake III Arena or Steam version to `/usr/local/games/quake3/baseq3`.
  * Set the memory split on the Pi platform.  See section 2.2 of the [Q3lite FAQ](https://github.com/cdev-tux/q3lite/wiki/Q3lite-FAQ) for details.
  * Be sure to set the necessary passwords in your server.cfg file located in ~/.q3a/baseq3.

### Documentation

  * [Q3lite wiki](https://github.com/cdev-tux/q3lite/wiki)
  * [Compiling and Installation Guide](https://github.com/cdev-tux/q3lite/wiki/Compiling-Install-Guide)
  * [Q3lite FAQ](https://github.com/cdev-tux/q3lite/wiki/Q3lite-FAQ)

### Q3lite on the Web

  * [Q3lite - Raspberry Pi Forums](https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=198680)

### Git branches

  * `master` stable - serious bug fixes only.
  * `dev` unstable - latest features/bug fixes - periodically promoted to stable.

### Versioning

Q3lite uses [Semantic Versioning.](http://semver.org)  
Release syntax is "Major_version.Minor_version.Patch_version".  
Post-release syntax is "Major_version.Minor_version.Patch_version+Commit_sha1".  
Full releases are tagged with the version number.  

### License

Q3lite is licensed under a [modified version of the GNU GPLv3](https://github.com/cdev-tux/q3lite/blob/master/COPYING.txt#L625) (or at your option, any later version). This license is also used by Doom 3.

### Contributing

Please submit patches as a GitHub pull request.  

  * One of the goals of Q3lite is to remove features that are too resource intensive to run well on embedded processors. This goes hand in hand with optimizing code to improve performance.
  * Q3lite is looking to add new lightweight features to help server administrators run their servers, as well as player features to enhance the Q3 experience.
  * The project also needs someone with [OpenGL ES](https://www.khronos.org/opengles) experience to help improve the renderer.
  * See the [Contributing Guide](https://github.com/cdev-tux/q3lite/wiki/Contributing) for details on how you can help.
  * If you enjoy Q3lite please consider giving the project a star at the top of this page.


### Credits

**Maintainer**

  * cdev-tux - [github.com/cdev-tux](https://github.com/cdev-tux)

**Significant contributions from:**  

  * Quake III Arena [source code](https://github.com/id-Software/Quake-III-Arena) - [id software](http://www.idsoftware.com)
  * ioquake3 contributors - [github.com/ioquake/ioq3](https://github.com/ioquake/ioq3)
  * Quake3e - [github.com/ec-/Quake3e](https://github.com/ec-/Quake3e)
  * SDL - [libsdl.org](https://www.libsdl.org)
  * Open Arena - [github.com/OpenArena](https://github.com/OpenArena)
  * ptitSeb - [github.com/ptitSeb/ioq3](https://github.com/ptitSeb/ioq3)
  * twolife - [github.com/twolife/ioq3](https://github.com/twolife/ioq3)
  * q3mme - [github.com/entdark/q3mme](https://github.com/entdark/q3mme)
  * Uber Demo Tools - [github.com/mightycow/uberdemotools](https://github.com/mightycow/uberdemotools)
  * and many other contributors


Quake III Arena screenshot copyright © 1999-2000 [id software](http://www.idsoftware.com).  
Raspberry Pi is a trademark of the [Raspberry Pi Foundation](https://www.raspberrypi.org/).  
Q3lite copyright © 2016 - 2019 cdev-tux - [github.com/cdev-tux](https://github.com/cdev-tux).  
All trademarks, logos and copyrights are the property of their respective owners.  
