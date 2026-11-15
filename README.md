# Goal Math League

A soccer penalty-shootout game for second-grade math practice. Solve the problem, tap the right answer in the goal, and score.

The whole game is one file, `index.html`, with no build step and no dependencies. Open it in a browser to play.

## What it covers

**Training ground** (always open)

| Match | Skill | How it plays |
|---|---|---|
| A. Subtraction Sprint | Subtract single digits (facts up to 18 − 9) | Dribble |
| B. Stack and Add | Add two-digit numbers in columns | Add in columns |

**Season**, following Grade 2 Module 4 (addition and subtraction within 200) in order

| Match | Skill | How it plays |
|---|---|---|
| 1. Warm-Up Passes | Add and take away tens | Dribble |
| 2. Bundle Up | Add two-digit numbers and make a new ten | Shootout |
| 3. Break a Ten | Subtract two-digit numbers and unbundle a ten | You are the goalie |
| 4. Big Scores | Add up to 200 in columns | Add in columns |
| 5. Cup Semi-Final | Subtract from numbers up to 200 | You are the goalie |
| 6. Cup Final | Everything together | Shootout |

## How the matches play

- **Shootout:** tap the right answer in the goal to shoot.
- **You are the goalie:** tap the right answer to dive and save the shot.
- **Dribble:** each right answer takes the player past a defender; two in a row sets up a goal.
- **Add in columns:** work the sum one digit at a time with a keypad, ones first, writing the new ten on the line.

A miss gets a hint and a second try. After a second miss, the coach walks through the problem step by step.

## Helper tools

Every match has three tools under the pitch: a tens-and-ones mat with bundle and break buttons, a number chart (1 to 200), and a scratch pad.

## Adding lessons

Problems are generated in the block between `/*LOGIC-START*/` and `/*LOGIC-END*/` in `index.html`. Each entry in `LEVELS` is one match: an id, a group (`training` or `season`), a kind (`shootout`, `keeper`, `dribble` or `long`), a name, a skill label, a rival team, and a `build` function that returns the list of questions.

Progress (stars, team name, team color) is saved in the browser on each device.
