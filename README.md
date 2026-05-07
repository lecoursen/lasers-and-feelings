# Lasers & Feelings: AI Game Master

An AI-powered Game Master for [Lasers & Feelings](https://johnharper.itch.io/lasers-feelings), a one-page tabletop RPG by John Harper. Uses a [GitHub Copilot CLI](https://docs.github.com/en/copilot/copilot-chat/using-github-copilot-chat-in-the-cli) custom agent to run a complete 55-minute session with dice rolling, narration, and pacing.

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

### 2. Create the game folder

```bash
mkdir -p ~/Desktop/lasers-and-feelings
```

### 3. Generate a scenario

Start a regular Copilot CLI session (not the agent) and ask it to generate a scenario:

```
Generate a new Lasers & Feelings scenario and save it to
~/Desktop/lasers-and-feelings/lasers-scenario.md.
Don't show me any details, just confirm when done.
```

The scenario file is GM-eyes-only. Don't share it with the players.

You can add flavor parameters:

- "Make it horror-themed"
- "Something with political intrigue"
- "Set it on a planet, not in space"
- "Include a moral dilemma, not just a villain to defeat"
- "Heavily involve [character name]'s backstory"

See `examples/lasers-scenario.md` for the expected format.

### 4. Create characters

Each player creates a character using the rules in the [PDF](https://johnharper.itch.io/lasers-feelings):

1. **Style:** Alien, Android, Dangerous, Heroic, Hot-Shot, Intrepid, or Savvy
2. **Role:** Doctor, Envoy, Engineer, Explorer, Pilot, Scientist, or Soldier
3. **Number (2-5):** High = better at LASERS (science, tech, reason). Low = better at FEELINGS (intuition, diplomacy, passion).
4. **Name:** Give your character a cool space adventure name.
5. **Goal:** Become Captain, Meet New Aliens, Shoot Bad Guys, Find New Worlds, Solve Weird Space Mysteries, Prove Yourself, or Keep Being Awesome.

As a group, also pick:

- **Two ship strengths:** Fast, Nimble, Well-Armed, Powerful Shields, Superior Sensors, Cloaking Device, Fightercraft
- **One ship problem:** Fuel Hog, Only One Medical Pod, Horrible Circuit Breakers, Grim Reputation

Save everything to `~/Desktop/lasers-and-feelings/lasers-characters.md`. Include backstories if you have them (the AI will weave them into the story). See `examples/lasers-characters.md` for the expected format.

**Tip:** You can also ask Copilot to generate characters: "Make a random character for Alex that complements the existing group in `~/Desktop/lasers-and-feelings/lasers-characters.md`."

## Game day

### 1. Set up the room

- Session leader opens a terminal and shares their screen so all players can see
- Everyone has their dice ready
- Allow 55 minutes for the session

### 2. Start the agent

Start the `lasers-gm` agent in Copilot CLI. The agent will automatically read the scenario and characters files, note the start time, and begin the game immediately with an opening scene.

### 3. Play

- **The AI narrates** the story and tells players when to roll dice
- **The session leader types** what players say and do (e.g., "Vesper tries to revive Captain Darcy" or "4L scans the derelict ship")
- **Players roll physical dice** and the session leader types the results (e.g., "she got 4 and 2")
- **Dialogue is formatted like a play script** (e.g., `SABLE: "The Silence is a gift."`), so each player reads their own character's lines from the screen
- **Helping:** Before any dice roll, another player can offer to help. They describe how and roll their own dice. If they succeed, the original roller gets +1 die.

### 4. Wrap up

The AI will steer toward a climax around the 45-minute mark and wrap up with an epilogue. After the session, ask it for a recap if you want one.

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
