# Platformer Level 1

A small 2D platformer digital prototype built with Phaser 3.

## Play online

https://uumenma.github.io/platformer-level-1/

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a desktop web browser such as Google Chrome.
3. Keep an internet connection available because Phaser 3 is loaded from a CDN.

No installation or build process is required.

## Controls

- Move left: Left Arrow
- Move right: Right Arrow
- Jump: Up Arrow or Space

## Main mechanic

The level uses a combo-jump mechanic:

1. Press Jump while the player is on the ground to perform a normal jump.
2. After landing, press Jump again quickly to perform a higher combo jump.
3. The combo jump must be triggered within approximately 250 milliseconds after landing.

Green boosters launch the player upward when the player lands on them while falling.

## Level elements

- Platforms: safe surfaces used to cross the level.
- Spikes: hazards that restart the level when touched.
- Gaps: falling into the void restarts the level.
- Star: the main goal; collecting it completes the level.
- Diamond: an optional collectible reward.
- Boosters: launch pads that help the player reach higher platforms.

## Where to edit the level

The current prototype does not yet use a separate text map. The level layout is currently created inside the `create()` function in `index.html`.

Look for the section named `CONSTRUCCION DEL NIVEL` and the calls to:

- `createPlat(startX, y, blocks)` to add platforms.
- `createSpikes(startX, y, blocks)` to add spike hazards.
- `boosters.create(x, y, 'booster')` to place boosters.
- `star` and `diamond` to position the collectibles.

The three level areas are marked in the source code as `SECCION 1`, `SECCION 2`, and `SECCION 3`.

## Physics and movement values

The current values are located in these parts of `index.html`:

- Gravity: `physics.arcade.gravity.y` in the Phaser configuration (currently `800`).
- Horizontal movement speed: `speed` inside `update()` (currently `135`).
- Normal jump strength: `-250` inside `update()`.
- Combo jump strength: `-480` inside `update()`.
- Booster launch strength: `-650` inside `triggerBooster()`.

These values can be adjusted to change how the game feels.

## Technology

- HTML5
- JavaScript
- Phaser 3.60.0

## Current prototype notes

The level layout and physics values are editable in the source code, but they have not yet been refactored into a separate text map and a single group of constants at the top of the file. Those are explicit requirements of the activity and should be completed before considering the technical checklist fully satisfied.
