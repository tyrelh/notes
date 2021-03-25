Hello everyone! Nice to see you all! Here is the latest alpha build of (tentatively titled) Ringtail! 🦝

Detailed changelog at the bottom of this devlog.

What is Ringtail? It is a small adventure and exploration game where you play as a raccoon disconnected from their family. In order to find your way you need to communicate with all the other creatures of this world. But to begin with, you don't understand their language! Upon talking to each new creature of a species you will learn a new word for from their language and you can understand more of what they are saying. The better you understand this worlds inhabitants, the more clues you uncover!

Ringtail is a game that I have been building mostly in the hours before my day job in the mornings.

Here are some of the interesting changes in this latest 0.0.3 alpha build.

## Speech Bubbles
I rewrote the dialog system to use speech bubbles placed above the characters that are speaking. Previously it used a dialog box that lived in the lower third of the screen. This worked fine but I really liked the idea of the speech bubbles living in the world with the characters. There is still work to do on it but I think it is coming along really nicely!

## Title Scene
The headlining feature of this build was suppose to be the new title scene but I think the speech bubbles are coming along really nicely. Regardless, the game has a "placeholder" title scene and options menu. Also a SceneChanger system that swaps scenes out with a fade effect. The transition effect might be placeholder as well but we will see how development progresses.

## 0.0.3 Alpha Demo Level
I added a few more things to this "world 1" demo level to start making it more of a "demo". There is a goal and end state now; you are trying to find the baby raccoon. And there are more crows to help give you hints about where to look but that also means there are more words to learn in the crow language!

## The Future
Here is a small list of features and enhancements to look forward to in the near future:
* Feedback when learning a new word
* Pause ability
* Options menu with text speed settings (eventually other accessibility settings as well such as more legible fonts)
* Save and continue game progress
* and much more...
Follow us on Twitter and Instagram @wolfpeachgames


## Changelog
### 0.0.3 Alpha - Title scene / Speech bubbles

#### Title scene:
* Placeholder logo
* Title menu
	* Button to start a new game functional
	* Options and Credits buttons load in placeholder scenes

#### Scene transitions:
* `SceneChanger` that can swap in scenes with a fade to black effect

#### Speech bubbles:
* Animated speech bubbles display on top at the NPC location
	* They are instanced on the root node and positioned using their parent's `global_position`
	* The dialog hint that displays when the player is in range indicates if you have talked to this NPC already or not (and thus if they will be able to teach you a new word for their language)

#### New assets:
* Baby raccoon sprite, no animations yet

#### Other improvements:
* `Crow` changes:
	* Expose their dialog API so there is no need to expose their children to access it
	* They land when the player isn't near
* Introduction text shown when first loading the world scene
* Dialog system can accept an optional callback function reference
* `VisibleBehindNode` allows modulating a sprite's opacity when the player walks behind the sprite
* `MovementNode` generalizes movement and movement animation for `KinematicBody2D`
* `World` script handles connecting the NPC dialog nodes to the Dialog Box
* `error` method in Log bypasses the `DEBUG` flag
* Colour constants in` GlobalConstants`

### 0.0.2 Alpha - Language Learning
#### Language learning:
* Speaking to an NPC for the first time will teach the player a random word from their language and dialog that the player doesn't already know
* Unknown words are obfuscated with jumbled symbols
* Known words are highlighted in the `SpeechBubble`
* `Crow` now has dialog and a `crow` language

#### Isometric view:
* Moved to an isometric camera angle

#### New assets:
* New isometric house and white fence
* WIP isometric sidewalk tileset
* Converted grass tileset to isometric
* New garbage bins (fun right?)
* Sprites and scenes for garbage, recycling, and compost bins

#### Other improvements:
* `Player` interaction collision shape smaller, more directional, and moves with `Player` animations
* Controls hint shown at game start and can be re-shown using the `I` key
* Logging system framework
* Currently only logging to console
* Uses `assert` to exclude logs from built project
* New `GameManager`
	* Currently just randomizes the randomizer seed on startup