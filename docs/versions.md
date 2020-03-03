---
Layout: page
title: Versions
permalink: /versions/
---

# Versions

***

Want more? Send an [email][mail], join [Discord][discord] or create a [GitHub issue][github-issue]

### Version 1.6.0

##### Release date: 03-03-2020

Improvements:

* Combined MainMenu and MobileMenu into one widget
* Combined HUD and MobileHUD into one widget, the switch is dynamic using the Platform Name
* Replace UI text by images, resulting in a clearer look.
* Greatly reduced package size by scaling and updating textures

### Version 1.5.0

##### Release date: 06-08-2019

New features:

* Ship selection
* Boss enemy
* Level complete option
    * On achieved score
    * On survived time

### Version 1.4.0

##### Release date: 20-11-2018

New features:

* Suicide enemy AI
* HTML5 support

Improvements:

* Improved enemy - player collision (e.g. better death handling in Enemy)

* Fixed issue where dead enemies would not explode
* Fixed issue where enemy movement was misbehaving

### Version 1.3.0

##### Release date: 02-07-2018

New features:

* Slow motion effect on player death

Improvements:

* Integrate Unreal Engine 4 built-in Damage System
* Integrate Pause Menu in HUD
* Split UI logic to Space Shooter 2D and Main Menu PlayerController objects
* Extract common HUD logic to BaseHUD object
* Added display resolutions enumeration for cleaner code
* Disable mobile action buttons on death
* Disabled tick method for actor when not used

* Fixed issue where dead enemies would still shoot projectiles
* Fixed issue where enabling homing on projectiles resulted in warnings (pending destroy)

### Version 1.2.0

##### Release date: 13-04-2018

New features:

* Weapon ammo system (including unlimited option)
* Weapon ammo pickup
* Score multiplier pickup
* Homing projectiles
* Homing projectile enemy
* Gamepad support

Improvements:

* Pickup chance code clean-up

### Version 1.1.0

##### Release date: 26-02-2018

New features:

* Mobile support
* Fire modes (tap, hold and automatic)
* Health regen option

### Version 1.0.0

##### Release date: 17-02-2018

* First release


[mail]: mailto:gracesgamesbv@gmail.com
[discord]: https://discord.gg/DBwFAES
[github-issue]: https://github.com/GracesGames/SpaceShooter2DKit/issues
