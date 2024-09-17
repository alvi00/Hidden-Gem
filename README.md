
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
