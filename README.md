# Persona Architect

**Stop sounding like an AI. Start sounding like yourself.**

`Persona Architect` is an open-source framework for code-assistant users. It provides a specialized "Interview Agent" that extracts your unique linguistic DNA—your rhythm, vocabulary, and quirks—and codifies them into a **skill file** that conforms to the [Claude Code skills](https://code.claude.com/docs/en/skills) format (YAML frontmatter + markdown body). The same format is used by Cursor and other tools following the [Agent Skills](https://agentskills.io) standard, so your persona skill is portable.

## Why use this?
Standard AI outputs are often overly polite, repetitive, and "robotic." By using a Persona Skill file, your AI collaborator will:
- Draft PR descriptions that look like you wrote them.
- Write documentation in your specific technical voice.
- Summarize threads using your preferred level of detail and snark/professionalism.

## How to Get Started

### 1. Initialize the Agent
Copy the content of [`prompts/persona-architect.md`](prompts/persona-architect.md) and paste it into:
- **Cursor:** Your "Agent" custom instructions or a new Chat with a specific prompt.
- **Claude Code:** Your system prompt configuration.

### 2. The Interview
The Agent will ask you 4-5 targeted questions. 
- **Be yourself.** Don't try to write "correctly." 
- Use your natural slang, sentence fragments, and formatting.

### 3. Save your DNA
The Agent will generate a full `SKILL.md` file (frontmatter + body) in a single code block. Save it as described below. For details on how skills work—discovery, invocation, optional fields—see [Claude Code: Extend Claude with skills](https://code.claude.com/docs/en/skills).

#### Where to save your skill
Save the file as `SKILL.md` inside a directory whose name matches the `name` in the frontmatter (e.g. `persona-jane`). Create the directory if it doesn't exist (e.g. `mkdir -p .claude/skills/persona-jane`).

| Tool         | Project (this repo only)              | Personal (all your projects)           |
| ------------ | ------------------------------------- | ------------------------------------- |
| **Claude Code** | `.claude/skills/<skill-name>/SKILL.md` | `~/.claude/skills/<skill-name>/SKILL.md` |
| **Cursor**   | `.cursor/skills/<skill-name>/SKILL.md` | `~/.cursor/skills/<skill-name>/SKILL.md` |

The Agent will suggest a `name` and remind you of the exact path after generating the file.

#### Using your persona skill
The generated skill is **user-invoked only**: the assistant will not apply your persona unless you ask. Invoke it by saying things like "use my persona", "write as me", "in my voice", or when you ask it to draft a ticket, document, or summary as you. You can also call it directly with `/skill-name` (e.g. `/persona-jane`).

## Repository Structure
- `prompts/`: Contains the "Interview Agent" system prompt.
- `templates/`: Persona skill template the agent uses to build your `SKILL.md`.

## Contributing
Have a better interview question? Want to support more AI tools? Pull requests are welcome!

---
*Created by victor-aguilars*