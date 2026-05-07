---
name: lasers-generate-character
description: >
  Generate a Lasers & Feelings character with backstory. Use when asked to "generate a character",
  "create a character for [name]", "make a L&F character", "add a character", or "write a backstory".
  Adds the character to ~/Desktop/lasers-and-feelings/lasers-characters.md.
---

# Lasers & Feelings Character Generator

Generate a character for a Lasers & Feelings RPG session and add it to `~/Desktop/lasers-and-feelings/lasers-characters.md`. Create the directory and file if they don't exist.

## Workflow

1. Ask the user for the **player's real name** (so you can tailor the character to them if they have preferences).
2. Ask if they have any preferences (style, role, number, name, goal) or if they want a fully random character.
3. Generate the character, choosing from the options below. If a characters file already exists, read it and make a character that **complements** the existing group (e.g., don't duplicate roles, vary the LASERS/FEELINGS spread).
4. Write a **2-3 paragraph backstory** that gives the character personality, history, and motivation. The backstory should explain how they ended up on the Raptor and hint at unfinished business or personal stakes.
5. Add the character to the characters file under the existing format. If the file doesn't exist yet, create it with the ship section (ask the group to pick ship strengths/problem, or generate defaults).
6. Show the user the finished character (stats + backstory) for approval before saving.

## Character creation options (from the original game)

**Style (pick one):** Alien, Android, Dangerous, Heroic, Hot-Shot, Intrepid, Savvy

**Role (pick one):** Doctor, Envoy, Engineer, Explorer, Pilot, Scientist, Soldier

**Number (2-5):** A high number means better at LASERS (technology, science, cold rationality, calm precise action). A low number means better at FEELINGS (intuition, diplomacy, seduction, wild passionate action).

**Goal (pick one or create your own):** Become Captain, Meet New Aliens, Shoot Bad Guys, Find New Worlds, Solve Weird Space Mysteries, Prove Yourself, Keep Being Awesome

**Name:** A cool space adventure name.

## Ship (only if creating the file for the first time)

**Two strengths (pick two):** Fast, Nimble, Well-Armed, Powerful Shields, Superior Sensors, Cloaking Device, Fightercraft

**One problem (pick one):** Fuel Hog (always needs energy crystals), Only One Medical Pod (and Captain Darcy is in it), Horrible Circuit Breakers (in battle, consoles tend to explode), Grim Reputation (Captain Darcy did some bad stuff)

## File format

The characters file should follow this structure:

```markdown
# Lasers & Feelings: Crew of the Raptor

## Ship

- **Strengths:** [Strength 1], [Strength 2]
- **Problem:** [Problem]

## Characters

- [Name], [Style] [Role], Number [N], Goal: [Goal]
- ...

---

## Backstories

### [Character Name]

[2-3 paragraphs]

### [Character Name]

[2-3 paragraphs]
```

## Guidelines

- Backstories should be fun and vivid, matching the game's tone (Star Trek meets Guardians of the Galaxy).
- Each character should have a clear personality hook that's easy to role-play.
- Include at least one detail that a GM could weave into a scenario (an old enemy, an unfinished mission, a secret, a debt).
- Every crew member has: a Consortium uniform (with built-in vacc-suit), a communicator-scanner (with universal translator), and a variable-beam phase pistol (set to stun, usually).
