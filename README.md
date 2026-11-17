# Goal Math League

A soccer penalty-shootout game for second-grade math practice. Solve the problem, tap the right answer in the goal, and score.

The game is `index.html` plus `phaser.min.js`, with no build step. Open `index.html` in a browser to play.

The pitch scenes run on [Phaser 3](https://phaser.io) (version 3.90, arcade-physics build, MIT license; see `PHASER-LICENSE.md`). The scoreboard, column worksheet, coach hints and helper tools are ordinary page elements.

## What it covers

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
- **Work in columns:** work the sum one digit at a time with a keypad, ones first. In addition, the new ten is written on the line.

A miss gets a hint and a second try. After a second miss, the coach walks through the problem step by step.

## Helper tools

Every match has three tools under the pitch: a tens-and-ones mat with bundle and break buttons, a number chart (1 to 200), and a scratch pad.

## Adding lessons

Problems are generated in the block between `/*LOGIC-START*/` and `/*LOGIC-END*/` in `index.html`. Each entry in `LEVELS` is one match: an id, a group (`training` or `season`), a kind (`shootout`, `keeper`, `dribble` or `long`), a name, a skill label, a rival team, and a `build` function that returns the list of questions.

Progress (stars, team name, team color) is saved in the browser on each device.

## Using your own artwork

Every picture on the pitch is a named texture. By default each one is drawn in code. To replace one with real art, add the image to an `assets` folder and list it in the `ART` map near the top of the pitch code in `index.html`:

```js
const ART = { 'ball': 'assets/ball.png', 'kp-idle': 'assets/keeper.png' };
```

The names and their sizes (in pitch units; the pitch is 560 by 400) are in the `SIZE` map just below `ART`. Images are scaled to those sizes, so draw them at two or more times that size for sharpness.

| Names | What they are |
|---|---|
| `bg-goal`, `bg-field` | Backgrounds for the goal view and the dribble view |
| `crowd-home`, `crowd-away`, `lights` | Crowd halves and floodlight glow |
| `net`, `posts`, `ball`, `shadow`, `confetti` | Goal parts, ball and effects |
| `kp-idle`, `kp-dive`, `kp-catch` | Keeper poses in the goal view (feet near the bottom centre) |
| `st-idle`, `st-kick`, `st-joy`, `st-sad` | Penalty taker poses, seen from behind |
| `pl-idle`, `pl-run1`, `pl-run2`, `pl-joy`, `df-idle`, `gk-field` | Dribble view: player, defender and keeper |

Built-in characters are drawn in the team colors. Custom images are shown as they are, without recoloring.
