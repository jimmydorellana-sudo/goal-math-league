# Goal Math League

A soccer penalty-shootout game for second-grade math practice. Solve the problem, tap the right answer in the goal, and score.

The game is `index.html` plus `phaser.min.js`, with no build step. Open `index.html` in a browser to play.

The pitch scenes run on [Phaser 3](https://phaser.io) (version 3.90, arcade-physics build, MIT license; see `PHASER-LICENSE.md`). The scoreboard, column worksheet, coach hints and helper tools are ordinary page elements.

The players, ball and goal nets are from the [Kenney Sports Pack](https://kenney.nl/assets/sports-pack) (CC0; see `assets/KENNEY-LICENSE.txt`). The pitch is drawn from above in the pack's grass colors.

## Games on the page

- **Goal Math League:** the soccer game described below.
- **Treasure Voyage:** JJ sails a pirate ship (tap the sea, or use the arrow keys) and lands on the island with the right answer. Right answers turn up clues and, on the last island, the treasure chest. A wrong landing draws cannon fire from the pirate ship and a hint; a second miss lets the pirates take that clue. Three voyages cover Lessons 9-10, Lessons 11-12, and a mix. Ships, islands, palms, rocks, cannonball and explosions are from the [Kenney Pirate Pack](https://kenney.nl/assets/pirate-pack); the chest and bottle are preview images from the Kenney Pirate Kit. Both are CC0 (licenses in `assets/`). The sprites are in `assets/pirate-atlas.png` and embedded in `index.html` as `ATLAS2`.
- **Math City art:** all eight buildings and the streets are renders of Kenney 3D models (CC0, licenses in `assets/`): the house and park from the [City Kit (Suburban)](https://kenney.nl/assets/city-kit-suburban); the warehouse, workshop, factory, office block, power plant and water tower from the [City Kit (Industrial)](https://kenney.nl/assets/city-kit-industrial); the street from the [City Kit (Roads)](https://kenney.nl/assets/city-kit-roads). The pictures are `assets/city-*.png`, embedded in `index.html`. In saved cities the old shop, school, fire station, apartment tower, stadium and clock tower become these buildings in the same order.
- **Splash Race:** JJ steers a speedboat (tap the water, or use the arrow keys) through the buoy gate with the right answer, racing the Red Racer to the finish line. A wrong gate spins the boat and brings up a hint; a second miss lets the rival through. Three races cover Lessons 9-10, Lessons 11-12, and a mix. The **Your boat** picker on the home screen sets the boat for both Splash Race and Treasure Voyage. Boats, buoys and the finish line are top-down renders of the 3D models in the [Kenney Watercraft Kit](https://kenney.nl/assets/watercraft-pack) (CC0, license in `assets/`), packed in `assets/boats-atlas.png` and embedded in `index.html` as `ATLAS4`.
- **Rocket Rescue:** three meteors fall toward the base, each with an answer. JJ taps the one with the right answer to zap it. Every wave adds a part to the rocket, and a right answer on the last wave launches it. A wrong tap crosses that meteor out and brings up a hint; a second miss lets the meteor land and the Meteors score. Three missions cover Lessons 9-10, Lessons 11-12, and a mix. Rocket parts, meteors, turret, craft and base are renders from the [Kenney Space Kit](https://kenney.nl/assets/space-kit) (CC0, license in `assets/`). The sprites are in `assets/space-atlas.png` and embedded in `index.html` as `ATLAS3`.
- **Math City:** every solved problem adds a piece to a building, and finished buildings fill a 12-lot city saved on the device. Problems are drawn from the matches under "This week in class". Buildings (house, park, shop, school, fire station, apartment tower, stadium, clock tower) unlock as the city grows, and a building finished with no mistakes gets a gold star. The buildings are drawn in code as small SVG pictures.

## What it covers

**This week in class** (always open; replaced as the class moves on)

| Match | Skill | How it plays |
|---|---|---|
| Hundreds Join In | Module 4, Lessons 9 and 10: add a two-digit number to a three-digit number, writing the new ten below the line | Work in columns |
| Read the Chips | Lessons 9 and 10: read two numbers from a place value chart and add them; bundles of ten plus loose ones | Shootout |
| Quick Take-Aways | Lesson 11: take a one-digit number from a two-digit number in your head, with and without unbundling | You are the goalie |
| Unbundle or Not? | Lessons 11 and 12: two-digit subtraction in columns, recording the new tens and ones above | Work in columns, starting with a yes or no decision |
| Weekly Cup | Lessons 9 to 12 mixed | Dribble |

**Training ground** (always open)

| Match | Skill | How it plays |
|---|---|---|
| A. Subtraction Sprint | Subtract single digits (facts up to 18 − 9) | Dribble |
| B. Stack and Add | Add two-digit numbers in columns | Work in columns |
| C. Stack and Subtract | Subtract two-digit numbers without regrouping | Work in columns |

**Season**, following Grade 2 Module 4 (addition and subtraction within 200) in order

| Match | Skill | How it plays |
|---|---|---|
| 1. Warm-Up Passes | Add and take away tens | Dribble |
| 2. Bundle Up | Add two-digit numbers and make a new ten | Shootout |
| 3. Break a Ten | Subtract two-digit numbers and unbundle a ten | You are the goalie |
| 4. Big Scores | Add up to 200 in columns | Work in columns |
| 5. Cup Semi-Final | Subtract from numbers up to 200 | You are the goalie |
| 6. Cup Final | Everything together | Shootout |

## How the matches play

- **Shootout:** swipe from the ball toward the right answer in the goal, or tap the answer.
- **You are the goalie:** drag the keeper under the right answer and let go, or tap the answer.
- **Dribble:** tap the pitch to run (or use the arrow keys). Run over the tile with the right answer at two gates, then tap the goal to shoot. The ball has real physics: it bounces off the posts and the keeper.

All match types are seen from above.
- **Work in columns:** work the sum one digit at a time with a keypad, ones first. In addition, the new ten is written on the line.

A miss gets a hint and a second try. After a second miss, the coach walks through the problem step by step.

## Helper tools

Every match has three tools under the pitch: a tens-and-ones mat with bundle and break buttons, a number chart (1 to 200), and a scratch pad.

## Adding lessons

Problems are generated in the block between `/*LOGIC-START*/` and `/*LOGIC-END*/` in `index.html`. Each entry in `LEVELS` is one match: an id, a group (`training` or `season`), a kind (`shootout`, `keeper`, `dribble` or `long`), a name, a skill label, a rival team, and a `build` function that returns the list of questions.

Progress (stars, team name, team color) is saved in the browser on each device.

## Artwork

The sprites are packed into one sheet, `assets/kenney-atlas.png`, with a frame table in `assets/kenney-atlas.json` (name: x, y, width, height). Both are also embedded in `index.html` (the `ATLAS` and `FRAMES` constants in the pitch code), so the game still runs from a single page plus `phaser.min.js`. If the sheet changes, the embedded copy has to be replaced as well.

| Frames | What they are |
|---|---|
| `red-b1` to `red-b5`, and the same for `blue`, `green`, `white` | Player bodies seen from above, five hair colors per kit (`red` is the pack's orange) |
| `yellow-b1`, `lime-b1`, `grey-b1` | Keeper-style kits |
| `*-arm`, `*-leg` (and `*-arm2`, `*-leg2` for darker skin), `bare-arm` | Limbs. Each player is a body plus two arms and two legs, posed and animated in code |
| `ball` | Soccer ball |
| `goal-top`, `goal-right` | Goals for the penalty view and the dribble view, built from the pack's net tile |

Team colors in the game are limited to kits that exist in the pack: blue, orange, white, yellow and lime. The green kit is left out because it is the same green as the grass.
