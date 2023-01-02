---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### Components

__HealthActor Interface__

I_HealthActor defines an abstract way to let an actor know it died.

__Health Component__

BP_HealthComponent handles taking damage, changes the maximum health and checking if the character is dead. Next to that, it handles the armor value and health regeneration options.

### Enemies
    
__Base Enemy__

BP_BaseEnemy is the generic enemy class. It serves as the base class for all enemy types and can be easily customized using the different property structures and components.
Adding a new enemy is as easy as creating a new row in the EnemyType data table and specifying its properties.

__Enemy Evade Component__

Used to implement the evade functionality of enemies. The options are defined by an EvadeOptions Structure.

__Enemy Movement Component__

Used to implement the movement functionality of the enemies. Support multiple types and options defined by a enumeration.

__Enemy Shooting Component__

Used to implement the shooting functionality of the enemies. Support multiple types and options defined by a enumeration.

### Game

__Main Menu Game Mode__

BP_MainMenuGameMode is the game mode and specifies the BP_MainMenuPlayerController as default controller. It is used as the game mode in the Main Menu and Mobile Main Menu maps.

__Space Shooter 2D Game Mode__

BP_SpaceShooter2DGameMode is the game mode and handles the current score, score multiplier, and game over actions. It is used as the game mode in the Test maps.

__Space Shooter 2D Game Instance__

BP_SpaceShooter2DGameInstance is the game instance and handles the ship selection options and currently selected ship. It is used by the game modes, the selection in the main menu and the correct spawning in the game maps.

__Game State__

BP_SpaceShooter2DGameState is the game state and handles the saving and loading of the save game.

__Save Game__

BP_SpaceShooter2DSaveGame is the save game and acts as a container for the save data (e.g. high score).

### Pickups

__Base Pickup__

BP_BasePickup is the parent class of all the pickup types. It handles the activation of the pickup when hitting the player, after which is destroys itself.

__Health Pickup__

BP_HealthPickup is a pickup that return a set amount of health to the player.

__Nuke Pickup__

BP_NukePickup is a pickup that adds a set amount of nuke ammo to the player.

__Score Multiplier Pickup__

BP_ScoreMultiplierPickup is a pickup that activates a score multiplier for a limited time.

__Shield Pickup__

BP_ShieldPickup is a pickup that activates the shield of the player.

__Weapon Ammo Pickup__

BP_WeaponAmmoPickup is a pickup that adds a set amount of weapon ammo to the player.

__Weapon Upgrade Pickup__

BP_WeaponUpgradePickup is a pickup that upgrades the weapon of the player.

__Pickup Interface__

I_Pickup adds the pickup events to the objects that implement it. BasePickup implements I_Pickup.

### Player

__Player__

BP_Player is the player of the game. It handles player input for movement, firing projectiles and activating nukes. Next to that, it handles the player ship visuals based on the selected ship and death consequences e.g. component deactivation. 
The other logic is handled in specific components to split complexity and logic.

The user can select different ships using the ship select menu in the main menu. These are defined in the PlayerShips DataTable.

__Player Movement Component__

BP_PlayerMovementComponent moves the player using the movement input it receives from BP_Player.

__Player Nuke Component__

BP_PlayerNukeComponent handles the activation and ammo management of the player nukes.

__Player Shield Component__

BP_PlayerShieldComponent handles the (de)activation of the player shield. It contains the logic for showing the shield when activate and playing the sound effects.

__Player Shooting Component__

BP_PlayerShootingComponent handles the shooting input it receives from BP_Player and fires projectiles.
It also contains logic for upgrading the weapon from single shot to double or even triple shot and managing the player ammo including the unlimited ammo option.
The player has three fire modes:
* Tap: fires one projectile per fire input  
* Hold: continuously fires projectiles until the fire input is released  
* Automatic: continuously firing projectiles until death

__Shield Actor Interface__

I_ShieldActor adds the ShieldVisibilityChanged event to the actors that implement it.

### PlayerControllers

__BP_MainMenuPlayerController__

Is responsible for creating and interacting with the Main Menu

__BP_SpaceShooter2DPlayerController__
 
Is responsible for creating and interacting with the HUD (Pause Menu and HUD changes).

### Projectiles

__Projectile__

BP_Projectile is the projectile fired by both the player and enemies. On collision it will try to damage the other actor and destroys itself.
It has several exposed options, for example: flipbook, movement speed and damage.

### Spawners

__Base Spawner__

BP_BaseSpawner is the parent class of all spawner types. It can be enabled/disabled (on/off) and activated/deactivated (spawning/sleeping).  
It contains methods for spawning an actor, spawning a specific enemy (type) and filter a list of enemies on type.

__Max Enemies Spawner__

BP_MaxEnemiesSpawner is a spawner that only spawns a specific type of enemy when the amount of this type of enemy in the level is below a threshold. For example, it only spawns a Meteor enemy when there are less than two Meteor enemies in the level.

__Pickup Spawner__

BP_PickupSpawner is the spawner for all pickups and uses a list of pickup spawnees. Each spawnee defines the type of pickup, its spawns per minute and the scale of the pickup.

__Wave Spawner__

BP_WaveSpawner is a spawner that spawns waves of enemies randomly chosen from the possible spawnees. It defines several customizable delays, for example delay between enemy spawns and delay between waves.

__Spawner Interface__

I_Spawner adds the activate and deactivate events to the spawners so other systems (e.g. the game mode) can activate and deactivate all spawners without a reference.

### UI

All user interfaces support mobile and gamepad input. Whether to highlight the selected button can be toggled using the ShouldHighlightFocusedButton variable.

__HUD__

The BP_HUD is the in-game user interface and shows the player the current health, ammo, score, score multiplier and amount of nuke ammo.  
It also defines the game over screen with the high score, current score, option to reset the high score and option to return to menu.  
The pause menu user interface is also integrated in the HUD and allows the player to continue the game or return to the main menu.  
When on a Mobile platform, the HUD dynamically switches to a more centered version with bigger button for touch input and shows the virtual joystick and buttons (fire, nuke and pause).  

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, contains the settings like help text and ship selection and quit the game.  