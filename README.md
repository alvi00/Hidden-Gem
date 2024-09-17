
# The Hidden Gems - Game Concept

## 1. High Concept Statement

**Title:** The Hidden Gems  
**Genre:** Survival  
**Platform:** PC (using Unity Game Engine)  
**Player Viewpoint:** First-Person Shooter (FPS)  

### General Story/Concept:
The player, a retired army soldier, wakes up on a serene beach after a peaceful sleep in a beach chair. He is approached by an NPC named David who recognizes him and asks for help. The NPC reveals that there are three islands nearby, each infested with dangerous monsters. The NPC promises the player 5 million dollars if he can retrieve a rare gem from each of the three islands. The player must defend against monsters, collect the gems, and return to the beach to claim his reward—all within a time limit of 3 in-game days.


### NPC (David and Player Dialogue):
David is a lapidarist who collects unique stones from different places. At the start, David recognizes the Player and asks for help.

**Dialogue Example:**

- **David:** "Hello, sir! Please wake up!"
- **Player:** "Huh? Oh, hi. Who are you?"
- **David:** "I’m David, a lapidarist. I collect unique stones from different places. But today, I need your help."
- **Player:** "Help? With what?"
- **David:** "There are three islands nearby, each infested with dangerous monsters. On each island, there's a rare gem. If you can retrieve all three gems and bring them back to me, I'll reward you with 5 million dollars."
- **Player:** "5 million dollars? Why me?"
- **David:** "I recognized you as a retired army soldier. Your skills are perfect for this task. But be warned, the monsters are fierce, and time is limited. You have only 3 in-game days to complete this mission."
- **Player:** "Alright, I'll do it. Where do I start?"
- **David:** "Your journey begins with the boat over there. It will take you to the islands. Good luck, and stay safe!"
- **Player:** "Thanks, David. I’ll be back with those gems."
- **David:** "I’m counting on you! Remember, time is of the essence."

### Monsters:
In "The Hidden Gems," the islands are inhabited by formidable monsters that serve as guardians of the rare gems. These creatures are the primary adversaries the player must overcome to complete the mission. 

#### Monster Behavior and Attack Mechanics:
- Monsters will engage the player within a certain proximity.
- Their primary attack method is a melee strike delivered with their hands, dealing **20 damage** to the player’s health per hit.
- To defeat a monster, the player must shoot it **three times** with their firearm. After the third shot, the monster will be eliminated.

### Islands:
The game features three distinct islands, each covered in a uniform grass texture to maintain visual consistency. Each island presents unique challenges, with **8 enemies** per island guarding the rare gems.

---

## 2. World and Mechanics

### World:
- **Setting:** The game is set on a beach with tropical, tranquil surroundings. The boundaries are defined by thick bushes.
- **Time of Day:** The game starts in the morning, giving a fresh and bright feel.
- **Key Landmarks:** 
  - **Windmill**: Serves as a visual landmark.
  - **Wooden Boat**: The player’s transportation between islands.
  - **Three Islands**: The locations where gems are found.
  - **Boundaries**: Prevent the player from leaving the designated area.

### Player Capabilities:
- **Movement:** W, A, S, D keys
- **Shooting:** Left mouse button
- **Reloading:** "R" key
- **Interacting with Objects (Boat/Gems/NPC):** "E" key
- **Health System:** Health packs restore health; player dies if health reaches zero.
- **Boat Navigation:** Drive the boat to travel between islands.

### NPC Capabilities:
- **Conversation:** The NPC initiates dialogue and explains the mission.
- **Transaction:** The NPC will exchange the gems for 5 million dollars.

### Enemy Behavior:
- **Melee Attack:** Enemies perform melee attacks.
- **Spawning:** Enemies spawn on islands and attack the player on sight.

### Lighting and Camera:
- **Lighting:** Direct lighting simulates sunlight for realism.
- **Camera:** FPS camera controlled by the mouse.

---

## 3. Triggers and Events

### Game Start Trigger:
- **Event:** The game begins when the player awakens on the beach and is approached by the NPC.
- **Trigger:** The NPC approaches and starts a dialogue.

### Objective Completion Trigger:
- **Event:** The player collects all three gems from the islands.
- **Trigger:** Picking up the final gem updates the player’s objectives.

### Winning Condition:
- **Event:** The player returns to the NPC with all three gems and receives 5 million dollars.
- **Trigger:** The player interacts with the NPC after collecting all gems.

### Losing Condition 1:
- **Event:** The player fails to return the gems within 3 in-game days.
- **Trigger:** Timer tracks the in-game days. If the limit is reached, the game ends in failure.

### Losing Condition 2:
- **Event:** The player’s health reaches zero.
- **Trigger:** The player dies due to enemy attacks.

### Health and Damage System:
- **Event:** Player takes damage from enemies and uses health packs to heal.
- **Trigger:** Enemy attacks reduce player health; health packs restore it.

---

## 4. Pseudocode for Events and Triggers

### Game Start Event:
```python
function gameStart() {
    playerAwakes();
    npcApproaches();
    npcDialogue("I need your help to retrieve gems from the islands.");
}
```

### Objective Update Event (Gem Collection):
```python
function collectGem(islandNumber) {
    player.collect(gem);
    gemsCollected += 1;

    if (gemsCollected == 3) {
        updateObjective("Return to the NPC to claim your reward.");
    }
}
```

### Winning Condition Event:
```python
function checkWinCondition() {
    if (player.interactsWith(npc) && gemsCollected == 3) {
        npc.giveReward(5000000);
        displayMessage("Congratulations! You have won!");
        endGame();
    }
}
```

### Losing Condition 1 (Time Expiry):
```python
function checkTime() {
    if (gameDaysPassed > 3) {
        displayMessage("You have run out of time. Game Over.");
        endGame();
    }
}
```

### Losing Condition 2 (Player Death):
```python
function checkPlayerHealth() {
    if (player.health <= 0) {
        displayMessage("You have died. Game Over.");
        endGame();
    }
}
```

### Boat Navigation:
```python
function useBoat() {
    if (player.interactsWith(boat)) {
        boat.start();
        navigateTo(islandNumber);
    }
}
```

---

## 6. In Summary
This prototype plan outlines the high concept, world, mechanics, and event logic of *The Hidden Gems*. The game offers a blend of exploration, combat, and time management, challenging the player to complete the objective within the given time frame.



# Brief Report

## Randomly Generated Scenario:


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

