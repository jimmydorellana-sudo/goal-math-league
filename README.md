# Goal Math League

A soccer penalty-shootout game for second-grade math practice. Solve the problem, tap the right answer in the goal, and score.

The whole game is one file, `index.html`, with no build step and no dependencies. Open it in a browser to play.

## What it covers

The six matches follow Grade 2 Module 4 (addition and subtraction within 200) in order:

| Match | Skill |
|---|---|
| 1. Warm-Up Passes | Add and take away tens |
| 2. Bundle Up | Add two-digit numbers and make a new ten |
| 3. Break a Ten | Subtract two-digit numbers and unbundle a ten |
| 4. Big Scores | Add up to 200 |
| 5. Cup Semi-Final | Subtract from numbers up to 200 |
| 6. Cup Final | Everything together |

A missed shot gets a hint and a second try. After a second miss, the coach walks through the problem step by step.

## Adding lessons

Problems are generated in the block between `/*LOGIC-START*/` and `/*LOGIC-END*/` in `index.html`. Each entry in `LEVELS` is one match: a name, a skill label, a rival team, and a `build` function that returns the list of questions.

Progress (stars, team name, team color) is saved in the browser on each device.
