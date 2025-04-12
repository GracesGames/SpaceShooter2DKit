---
Layout: page
title: Versions
permalink: /versions/
---

# Versions

***

### Version 1.8.1

##### Release date: Under Review

Improvements:

* Fixed issue where the enemy movement speed was inconsistent for different frame rates

### Version 1.8.0

##### Release date: 02-01-2023

New features:

* Complete visual redesign for all actors and levels
* Moved from portrait mode to landscape mode
* Added EnemyShootDirection modes: EjectDirection and PlayerPosition
* Added armor option to the Health Component

Improvements:

* Unified enemy projectile and player projectile to a single projectile with exposed options
* Refactored and simplified player weapon setup and logic

* Extracted enemy movement logic to EnemyMovementComponent
* Extracted enemy shooting logic to EnemyShootingComponent
* Extracted enemy evade logic to EnemyEvadeComponent

* Extracted player movement logic to PlayerMovementComponent
* Extracted player shooting logic to PlayerShootingComponent
* Extracted player nuke logic to PlayerNukeComponentComponent
* Extracted player shield logic to PlayerShieldComponent

* Combined level bounds into a single hollow volume
* Cleaned up spawner logic

### Version 1.7.0

##### Release date: 11-09-2021

Improvements:

* Replaced BaseCharacter logic with HealthComponent
* Reparented Player to Pawn instead of PaperCharacter, allowing more collision shapes
* Improved fire logic and projectile direction
* Improve Main Menu background and added Tiling to scrolling space background material

* Fixed issue where ship select initial ship was not correct

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
