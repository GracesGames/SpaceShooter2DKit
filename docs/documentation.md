---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### Characters

__Base Character__

BP_BaseCharacter is the parent class of the base enemy and player. It implements the changing of Flipbooks function and the health and health regen systems.  
The health system handles taking damage, changes the maximum health and checking if the character is dead.  
The health regen system, regenerates the character's health after not taking damage for a while.
    
__Base Enemy__

BP_BaseEnemy is the generic enemy class. It serves as the base class for all enemy types and can be easily customized using the different property structures.  
Adding a new enemy is as easy as creating a new rule in the EnemyType data table and specifying its properties.

__Player__

BP_Player is the player of the game. It handles player input for movement, firing projectiles and activating nukes.  
The player support movement using the built-in Unreal Engine physics of simple sweep movement.  
It also allows for several skills using the different pickups like activating a shield and upgrading its weapon from single shot to double or even triple shot.  
The player has three fire modes:
* Tap: fires one projectile per fire input  
* Hold: continuously fires projectiles until the fire input is released  
* Automatic: continuously firing projectiles until death

The player also holds the variable to toggle the mobile user interface.

### Game

__Game Mode__

BP_SpaceShooter2D is the game mode and handles the current score and game over actions.

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

BP_NukePickup is a pickup that adds one nuke ammo to the player.

__Shield Pickup__

BP_ShieldPickup is a pickup that activates the shield of the player.

__Weapon Upgrade Pickup__

BP_WeaponUpgradePickup is a pickup that upgrades the weapon of the player.

### Projectiles

__Base Projectile__

BP_BaseProjectile is the parent class of the enemy and player projectile. It handles the initialization of direction and speed and checks if the target is damageable.

__Enemy Projectile__

BP_EnemyProjectile is the projectile fired by enemies and only collides with the player. On collision is damages the player an amount specified by the public variable and destroys itself.

__Player Projectile__

BP_PlayerProjectile is the projectile fired by the player and only collides with the enemies. On collision is damages the enemy an amount specified by the public variable and destroys itself.

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

### UI

__HUD__

BP_HUD is the in-game user interface and shows the player the current score, health, and amount of nuke ammo.  
It also defines the game over screen with the high score, current score and a return to menu button.  
The MobileHUD version is created for mobile support. It is more centered to show the virtual joystick and buttons (fire, nuke and pause).

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, change settings (e.g. resolutions), show the controls and quit the game.  
The MobileMainMenu version is created for mobile support. It does not show the resolution options.

__Pause Menu__

BP_PauseMenu is the pause menu user interface and allows the player to continue the game, reset the high score and return to the main menu.  
The MobilePauseMenu version is created for mobile support. It has bigger buttons to better support touch input.