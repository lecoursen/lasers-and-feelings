# Lasers & Feelings: AI Game Master

An AI-powered Game Master for [Lasers & Feelings](https://johnharper.itch.io/lasers-feelings), a one-page tabletop RPG by John Harper. Uses a [GitHub Copilot CLI](https://docs.github.com/en/copilot/copilot-chat/using-github-copilot-chat-in-the-cli) custom agent to run a complete session (configurable length, default 55 minutes) with dice rolling, narration, and pacing.

One person acts as the **session leader**: they type player actions into the terminal, and the AI responds with narration and dice roll requests. The screen is shared so all players can read along. Dialogue is formatted like a play script so each player reads their own character's lines aloud.

## What you need

- [GitHub Copilot CLI](https://docs.github.com/en/copilot/copilot-chat/using-github-copilot-chat-in-the-cli) installed and authenticated
- Physical dice (d6s, at least 3 per player) or a dice-rolling app
- The [Lasers & Feelings PDF](https://johnharper.itch.io/lasers-feelings) for character creation reference
- 2-4 players + 1 session leader (the session leader can also be a player)

## Prep phase (before game day)

Do this a day or more before the session. It takes about 10 minutes.

### 1. Install the agent

Copy `lasers-gm.md` from this repo to your Copilot agents folder:

```bash
cp lasers-gm.md ~/.copilot/agents/lasers-gm.md
```

### 2. Install the skills

The repo includes two Copilot CLI skills for session prep. Copy them to your personal skills directory:

```bash
cp -r .github/skills/lasers-generate-scenario ~/.copilot/skills/
cp -r .github/skills/lasers-generate-character ~/.copilot/skills/
```

Restart Copilot CLI (or run `/skills reload` in an active session) to pick them up.

### 3. Create the game folder

```bash
mkdir -p ~/Desktop/lasers-and-feelings
```

### 4. Generate a scenario

Start a regular Copilot CLI session (not the agent) and say:

```
Generate a Lasers & Feelings scenario
```

Copilot will invoke the `lasers-generate-scenario` skill, which has all the game context, structure, and inspiration tables baked in. It saves the result to `~/Desktop/lasers-and-feelings/lasers-scenario.md` without showing you spoilers. If a characters file already exists, it weaves in backstory connections.

You can add flavor:

- "Generate a Lasers & Feelings scenario, but make it horror-themed"
- "Generate a L&F scenario with political intrigue"
- "Generate a scenario set on a planet, not in space"

See `examples/lasers-scenario.md` for what a finished scenario looks like.

### 5. Create characters

Each player needs a character. You can create them by hand (see the [PDF](https://johnharper.itch.io/lasers-feelings) for options) or use the skill:

```
Create a Lasers & Feelings character for Alex
```

The `lasers-generate-character` skill will ask for preferences (or generate a fully random character), write a backstory, and add the character to `~/Desktop/lasers-and-feelings/lasers-characters.md`. It complements the existing group automatically (no duplicate roles, varied LASERS/FEELINGS spread).

As a group, also pick ship strengths and a problem (the skill handles this when creating the first character).

See `examples/lasers-characters.md` for the expected format.

## Game day

### 1. Set up the room

- Session leader opens a terminal and shares their screen so all players can see
- Everyone has their dice ready
### 2. Start the agent

Start the `lasers-gm` agent in Copilot CLI. The agent will ask how many minutes you have (default: 55), read the scenario and characters files, note the start time, and begin the game immediately with an opening scene. All pacing adjusts to the session length you choose.

### 3. Play

- **The AI narrates** the story and tells players when to roll dice
- **The session leader types** what players say and do (e.g., "Vesper tries to revive Captain Darcy" or "4L scans the derelict ship")
- **Players roll physical dice** and the session leader types the results (e.g., "she got 4 and 2")
- **Dialogue is formatted like a play script** (e.g., `SABLE: "The Silence is a gift."`), so each player reads their own character's lines from the screen
- **Helping:** Before any dice roll, another player can offer to help. They describe how and roll their own dice. If they succeed, the original roller gets +1 die.

### 4. Wrap up

The AI will steer toward a climax around the 80% mark and wrap up with an epilogue. After the session, ask it for a recap if you want one.

## Quick dice reference

Roll d6s and compare each die to your character's number:

| Type | Success condition | When to use |
|------|------------------|-------------|
| LASERS | Roll **under** your number | Technology, science, rational action |
| FEELINGS | Roll **over** your number | Intuition, diplomacy, passionate action |

| Successes | Result |
|-----------|--------|
| 0 | It goes wrong |
| 1 | Partial success with a complication |
| 2 | Full success |
| 3 | Critical success with a bonus |
| Exact number | LASER FEELINGS: counts as a success + ask the GM one honest question |

## File structure

```
~/Desktop/lasers-and-feelings/
├── lasers-scenario.md      # GM-eyes-only adventure (generated during prep)
└── lasers-characters.md    # Player characters + ship stats
```

## Credits

[Lasers & Feelings](https://johnharper.itch.io/lasers-feelings) is by John Harper. The game format is open for hacking and remixing under a [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/).
