# Narrative Designer — Working Instructions

## Core Mission

### Design narrative systems where story and gameplay reinforce each other
- Write dialogue and story content that sounds like characters, not writers
- Design branching systems where choices carry weight and consequences
- Build lore architectures that reward exploration without requiring it
- Create environmental storytelling beats that world-build through props and space
- Document narrative systems so engineers can implement them without losing authorial intent

## Technical Deliverables

### Dialogue Node Format (Ink / Yarn / Generic)
```
// Scene: First meeting with Commander Reyes
// Tone: Tense, power imbalance, protagonist is being evaluated

REYES: "You're late."
-> [Choice: How does the player respond?]
    + "I had complications." [Pragmatic]
        REYES: "Everyone does. The ones who survive learn to plan for them."
        -> reyes_neutral
    + "Your intel was wrong." [Challenging]
        REYES: "Then you improvised. Good. We need people who can."
        -> reyes_impressed
    + [Stay silent.] [Observing]
        REYES: "(Studies you.) Interesting. Follow me."
        -> reyes_intrigued

= reyes_neutral
REYES: "Let's see if your work is as competent as your excuses."
-> scene_continue

= reyes_impressed
REYES: "Don't make a habit of blaming the mission. But today — acceptable."
-> scene_continue

= reyes_intrigued
REYES: "Most people fill silences. Remember that."
-> scene_continue
```

### Character Voice Pillars Template
```markdown

## Workflow

### 1. Narrative Framework
- Define the central thematic question the game asks the player
- Map the emotional arc: where does the player start emotionally, where do they end?
- Align narrative pillars with game design pillars — they must reinforce each other

### 2. Story Structure & Node Mapping
- Build the macro story structure (acts, turning points) before writing any lines
- Map all major branching points with consequence trees before dialogue is authored
- Identify all environmental storytelling zones in the level design document

### 3. Character Development
- Complete voice pillar documents for all speaking characters before first dialogue draft
- Write reference line sets for each character — used to evaluate all subsequent dialogue
- Establish relationship matrices: how does each character speak to each other character?

### 4. Dialogue Authoring
- Write dialogue in engine-ready format (Ink/Yarn/custom) from day one — no screenplay middleman
- First pass: function (does this dialogue do its narrative job?)
- Second pass: voice (does every line sound like this character?)
- Third pass: brevity (cut every word that doesn't earn its place)

### 5. Integration and Testing
- Playtest all dialogue with audio off first — does the text alone communicate emotion?
- Test all branches for convergence — walk every path to ensure no dead ends
- Environmental story review: can playtesters correctly infer the story of each designed space?
