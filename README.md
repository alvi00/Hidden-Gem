# Brief Report

## Randomly Generated Scenario:

*(Provide details of the scenario here)*

---

## Unity Store Assets

### Simple Free Beach Models
- **Type of Asset:** 3D Objects  
- **Where it is used:** Main scene, main island to decorate the island  
- **URL:** [https://assetstore.unity.com/packages/3d/props/simple-free-beach-models-287370](https://assetstore.unity.com/packages/3d/props/simple-free-beach-models-287370)

### LowPoly Survival Character Rio
- **Type of Asset:** 3D Objects  
- **Where it is used:** NPC talk  
- **URL:** [https://assetstore.unity.com/packages/3d/characters/humanoids/lowpoly-survival-character-rio-273074](https://assetstore.unity.com/packages/3d/characters/humanoids/lowpoly-survival-character-rio-273074)

### First Aid Jar
- **Type of Asset:** 3D Objects  
- **Where it is used:** To let user gain health as a health kit  
- **URL:** [https://assetstore.unity.com/packages/3d/props/first-aid-jar-285565](https://assetstore.unity.com/packages/3d/props/first-aid-jar-285565)

### Stylized Crystal
- **Type of Asset:** 3D Objects  
- **Where it is used:** To collect gem  
- **URL:** [https://assetstore.unity.com/packages/3d/props/stylized-crystal-77275](https://assetstore.unity.com/packages/3d/props/stylized-crystal-77275)

### Fantasy Monster - Skeleton
- **Type of Asset:** 3D Objects  
- **Where it is used:** Skeleton model as enemy  
- **URL:** [https://assetstore.unity.com/packages/3d/characters/humanoids/fantasy-monster-skeleton-35635](https://assetstore.unity.com/packages/3d/characters/humanoids/fantasy-monster-skeleton-35635)

### Island Assets
- **Type of Asset:** 3D Objects  
- **Where it is used:** To have island in game  
- **URL:** [https://assetstore.unity.com/packages/3d/environments/island-assets-56989](https://assetstore.unity.com/packages/3d/environments/island-assets-56989)

### Low Poly Shooter Pack - Free Sample
- **Type of Asset:** 3D Objects  
- **Where it is used:** To have shooting character in game  
- **URL:** [https://assetstore.unity.com/packages/templates/systems/low-poly-shooter-pack-free-sample-144839](https://assetstore.unity.com/packages/templates/systems/low-poly-shooter-pack-free-sample-144839)

---

## Online Tutorials

### Tutorial 1
- **Details of what the tutorial helped you with:** Helped me to learn how to pick up an object  
- **Tutorial URL:** [How To Pick Up an Item - Unity](https://youtu.be/BLfNP4Sc_iA?si=Q3z69lZEmXzw4Fim)

### Tutorial 2
- **Details of what the tutorial helped you with:** Helped me to understand how the health bar works  
- **Tutorial URL:** [Health Bar Tutorial](https://youtu.be/BLfNP4Sc_iA?si=Q3z69lZEmXzw4Fim)

---

## Major Changes Made Since Submitting Prototype Plan

- **Change Made:** Used static dialogue images without character animation  
- **Reason for the Change:** Did not find any free character animation in Unity  

---

## Known Bugs or Limitations

### Bug 1
- **Issue:** Player cannot drive the boat  
- **Details:** Attempted to disable player control and enable boat control, but it did not work. Used collider and made it triggered. When the user presses 'E,' it starts the timeline and moves to another island.

---

## The Player Controller

- **Controller Asset Name:** P_LPSP_FP_CH  
- **Type of Controller Used:** Unity Asset Store Controller  
- **Controller Details:**
  - W to move forward
  - A to move left
  - D to move right
  - S to move backward
  - T to inspect gun
  - R to reload
  - Q to change gun
  - Mouse scroll to change gun
  - Mouse movement to look around
  - E to trigger events

---

## End Conditions

### Collect Gem in Time
- **Script:** `GameTimer.cs`  
- **Details:** Starts a timer of 60s in each island. The user must collect the gem within 1 minute; otherwise, an end-game canvas opens, and the user can restart the game.

### Death by Zombies
- **Script:** `player_death.cs`  
- **Details:** There are skeleton zombies, and a slider tracks the player's health. Health decreases by 20% on collision with each zombie. After 5 collisions, the player dies, the end-game canvas opens, and the user can restart the game.

---

## Events

### Event 1: Assigned - Skeleton Attack
- **Script:** `SkeletonScript.cs`  
- **Object:** Skeleton@Attack  
- **Details:** Attached to the skeleton. If the skeleton is hit 3 times by bullets, it dies.

### Event 2: Assigned - Bullet Attack
- **Script:** `Projectile.cs`  
- **Object:** `P_LPSP_WEP_Handgun_03` (Child of `character_for_island_island`)  
- **Details:** Detects bullet collisions with objects tagged as skeletons. After 3 collisions, the skeleton dies.

### Event 3: Assigned - Player Health
- **Script:** `player_health.cs`  
- **Object:** `character_for_island_island`  
- **Details:** Controls the health bar, indicating the remaining health. After picking up a health kit, it refills the bar.

### Event 4: Assigned - Pick Up Stone
- **Script:** `pick_up_stone.cs`  
- **Object:** `crystal_17_2`  
- **Details:** If a game object tagged as Player collides with the gem, it activates. When the user presses 'E,' they collect the gem.

### Event 5: Assigned - Dialogue Box
- **Script:** `npcconversation.cs`  
- **Object:** `Rio`  
- **Details:** Opens a dialogue box when the player collides with Rio. Pressing the left key changes the dialogue.

### Event 6: Assigned - Pause Menu
- **Script:** `pause_game.cs`  
- **Object:** `pausemenu`  
- **Details:** Pauses the game by setting `Time.timeScale = 0` and shows a pause canvas. The resume button restores the game by setting `Time.timeScale = 1`. The exit button allows the user to exit the game.

### Event 7: Assigned - Go to Another Scene
- **Script:** `main_scene_to_first_island.cs`  
- **Object:** `Boat`  
- **Details:** Attached to the boat. If the player collides with the boat, a canvas appears. Pressing 'E' plays the timeline and changes the scene.

### Event 8: Assigned - Change Scene and Check Gem Collection
- **Script:** `level_changer.cs`  
- **Object:** `boat_for_islamd1`  
- **Details:** If the player has not collected the gem, the boat tells them to collect it first. After collecting the gem and pressing 'E,' the player moves to the next scene (island).

### Event 9: Assigned - Player Win and End Game
- **Script:** `last_npc_talk.cs`  
- **Object:** `Rio`  
- **Details:** After the player collects three gems and collides with Rio, a dialogue box opens, indicating the player has won the game and can exit.

### Event 10: Assigned - Game Time
- **Script:** `GameTimer.cs`  
- **Object:** `GameTimeManager`  
- **Details:** Assigns 60 seconds per scene. If the player completes the task within the time, nothing happens. If not, a "lose" canvas opens, allowing the user to restart the game.

