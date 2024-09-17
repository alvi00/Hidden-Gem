1. High Concept Statement
Title: The Hidden Gems
Genre: Survival
Platform: PC (using Unity Game Engine)
Player Viewpoint: First-Person Shooter (FPS)
General Story/Concept:
The player, a retired army soldier, wakes up on a serene beach after a peaceful sleep in a beach chair. He is approached by an NPC named David who recognizes him and asks for help. The NPC reveals that there are three islands nearby, each infested with dangerous monsters. The NPC promises the player 5 million dollars if he can retrieve a rare gem from each of the three islands. The player must defend against monsters, collect the gems, and return to the beach to claim his reward—all within a time limit of 3 in-game days.
This image shows full story in a flow chart:

- NPC(David and Player Dialogue):
David is a lapidarist. He collects uniqe stones from deferent places. At start David will recognizes Player and ask for help. The dialouge will be like this.
David: "Hello, sir! Please wake up!"
Player: "Huh? Oh, hi. Who are you?"
David: "I’m David, a lapidarist. I collect unique stones from different places. But today, I need your help."
Player: "Help? With what?"
David: "There are three islands nearby, each infested with dangerous monsters. On each island, there's a rare gem. If you can retrieve all three gems and bring them back to me, I'll reward you with 5 million dollars."
Player: "5 million dollars? Why me?"
David: "I recognized you as a retired army soldier. Your skills are perfect for this task. But be warned, the monsters are fierce, and time is limited. You have only 3 in-game days to complete this mission."
Player: "Alright, I'll do it. Where do I start?"
David: "Your journey begins with the boat over there. It will take you to the islands. Good luck, and stay safe!"
Player: "Thanks, David. I’ll be back with those gems."
David: "I’m counting on you! Remember, time is of the essence."
- Monsters:
In "The Hidden Gems," the islands are inhabited by formidable monsters that serve as guardians of the rare gems. These creatures are the primary adversaries the player must overcome to complete the mission. Each monster is highly territorial and will aggressively defend the area around the gem it protects.
Monsters Behavior and Attack Mechanics:
The monsters are programmed to engage the player whenever they come within a certain proximity. Their primary attack method is a powerful melee strike delivered with their hands. When the player approaches too closely, the monster will initiate an attack sequence, attempting to inflict damage through a direct hand-to-hand strike.
Each successful attack by the monster deals a significant 20 damage to the player’s health. This damage can quickly add up, making it crucial for the player to strategize their approach and avoid unnecessary close encounters.
Combat and Defeating the Monsters:
The player is equipped with a firearm to defend against these threats. To defeat a monster, the player must shoot it a total of three times. Each bullet weakens the monster, and after the third shot, the monster will be eliminated. The player must be precise and efficient in their attacks, as the monsters are relentless and will continue to pursue the player until they are defeated.
Given that the monsters protect the gems, defeating them is a mandatory task for the player. The gems are the ultimate objective of the game, and the player must retrieve them from each of the three islands. The monsters' role as protectors of the gems adds a layer of challenge, as the player must not only navigate the islands but also survive these dangerous encounters.
An Example image of how the monster looks like:


- Island:
The game features three distinct islands, each covered in a uniform grass texture to maintain visual consistency across the game world. Although the islands share the same general appearance, they each present unique challenges.
On each island, the player must defend against eight enemies. These enemies are strategically positioned to guard the rare gems that the player needs to collect. The islands are designed to be easily located at the start of the mission, ensuring that the player can quickly find and navigate between them without unnecessary delays.
The uniformity in design allows the player to focus on the strategic combat required to defeat the enemies and retrieve the gems, while the grass texture adds to the natural, tropical feel of the environment.
This image shows how the island will look like:

The yellow object is Gems and the red are enemys!
2. World and Mechanics
World:
The game is set on a beach with tropical, tranquil surroundings. The boundaries of the game world are defined by thick bushes, preventing the player from straying too far from the playable area. The time of day starts in the morning, giving a fresh and bright feel to the game environment, but the player needs to complete the objective within 3 in-game days.
Key Environmental Features:
Windmill: Located on the beach, the windmill serves as a visual landmark, enhancing the beach ambiance and helping players orient themselves.
Wooden Boat: The player’s means of transportation between the islands, docked at the beach, ready for use.
Three Islands: The islands are distinct, each offering unique challenges and enemy types, and house the gems the player must retrieve.
Boundaries: Thick bushes surrounding the beach area prevent the player from leaving the designated play area.
An image to understand the Map.

Mechanics:
Player Capabilities:
Movement: The player moves using W, A, S, D keys.
Shooting: The player shoots using the left mouse button.
Reloading: The player reloads their weapon using the "R" key.
Interacting with Objects (Boat/Gems/NPC): The player interacts with objects using the "E" key.
Health: The player can take damage and use health packs to heal.
Death: If the player’s health reaches zero, they die and lose the game.
Boat Navigation: The player can drive the boat to travel between the islands.
NPC Capabilities:
Conversation: The NPC can initiate a dialogue with the player, explaining the mission and offering the reward.
Transaction: The NPC will take the three gems from the player and give 5 million dollars in return.
Enemy Behavior:
Melee Attack: Enemies can perform melee attacks to damage the player.
Spawning: Enemies spawn on the islands and attack the player on sight.
Lighting and Camera:
Lighting: The game features direct lighting to simulate sunlight, enhancing the realism of the beach environment.
Camera: The game uses an FPS camera, controlled by the mouse, allowing the player to view and interact with the world from a first-person perspective.

3. Triggers and Events
Game Start Trigger:
Event: The game begins when the player awakens on the beach and is approached by the NPC.
Trigger: The NPC approaches and starts a dialogue.
Objective Completion Trigger:
Event: The player collects all three gems from the islands.
Trigger: The player picks up the final gem, triggering an event that updates the player’s objectives.
Winning Condition:
Event: The player returns to the NPC with all three gems and receives the 5 million dollars.
Trigger: The player interacts with the NPC after collecting all gems, completing the game.
Losing Condition 1:
Event: The player fails to return the gems within 3 in-game days.
Trigger: A timer tracks the in-game days. If the time limit is reached without completing the objectives, the game ends in failure.
Losing Condition 2:
Event: The player’s health reaches zero due to enemy attacks.
Trigger: The player dies if their health depletes, resulting in a game over.
Health and Damage System:
Event: The player takes damage from enemies and can restore health using health packs.
Trigger: Enemy attacks reduce the player’s health; health packs restore it.
Event Trigger Diagram:


4. Pseudocode for Events and Triggers
Below is simple pseudocode outlining the logic for key events:
Game Start Event:
function gameStart() {
    playerAwakes();
    npcApproaches();
    npcDialogue("I need your help to retrieve gems from the islands.");
}
Objective Update Event (Gem Collection):
function collectGem(islandNumber) {
    player.collect(gem);
    gemsCollected += 1;
    
    if (gemsCollected == 3) {
        updateObjective("Return to the NPC to claim your reward.");
    }
}
Winning Condition Event:
function checkWinCondition() {
    if (player.interactsWith(npc) && gemsCollected == 3) {
        npc.giveReward(5000000);
        displayMessage("Congratulations! You have won!");
        endGame();
    }
}
Losing Condition 1 (Time Expiry):
function checkTime() {
    if (gameDaysPassed > 3) {
        displayMessage("You have run out of time. Game Over.");
        endGame();
    }
}
Losing Condition 2 (Player Death):
function checkPlayerHealth() {
    if (player.health <= 0) {
        displayMessage("You have died. Game Over.");
        endGame();
    }
}
Boat Navigation:
function useBoat() {
    if (player.interactsWith(boat)) {
        boat.start();
        navigateTo(islandNumber);
    }
}
6. In Summary
This prototype plan outlines the high concept, world, mechanics, and event logic of The Hidden Gems. The game offers a blend of exploration, combat, and time management, challenging the player to complete the objective within the given time frame. The images and diagrams will further clarify the mechanics and flow of the game.

