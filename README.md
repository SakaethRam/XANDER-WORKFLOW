# Xander Workflow

**AI-Augmented Generalist | The Communication Layer Between Product and Engineering**

**Xander Workflow** serves as an AI-augmented generalist and the dedicated cross-functional communication layer between Product and Engineering teams. It bridges the gap in jargon and terminology between two distinct domains, ensuring both teams work from a single, shared understanding.

This repository is a portable **instruction and workflow preset** for the Xander agent. It runs inside a shared [Switch Console](https://github.com/sandbox-quantum/switch) room, powered by the AI CLI provider of your choice (Cursor, Codex, or Claude).

> **Scope:** This repository contains instructions, context, and workflows. It is not a messaging application, a backend service, or an AI model.

---

## 1. Overview

Product knows customers, priorities, and outcomes. Engineering knows feasibility, architecture, and constraints. Different vocabularies lead to ambiguous requirements, repeated clarification, and lost time.

Xander sits in a shared room with both teams and translates **meaning and implications**, not just words. It clarifies, translates, and surfaces trade-offs, while leaving every decision to people.

Xander is a neutral intermediary. It is not a coding assistant, project manager, or decision-maker.

## 2. How It Works

| Component | Role |
|---|---|
| **Switch Console** | The communication infrastructure that connects people and AI agents through shared rooms. |
| **Xander (AI generalist agent)** | Runs on the provider you configure: Cursor, Codex, or Claude. |
| **This repository** | The agent's working directory, holding its permanent instructions, context, and workflows. |

```
 Product ──┐                          ┌─ reads AGENTS.md, context/, workflows/
           ├─►  Switch room  ◄───────►│  Xander (provider of your choice)
 Engineers ┘                          └─ working directory = this repo
```

## 3. Prerequisites

Complete these before importing the preset.

### 3.1 Switch Console

Switch Console is the host application for the shared room.

- **Source and installation:** [github.com/sandbox-quantum/switch](https://github.com/sandbox-quantum/switch)
- **Documentation:** [docs.flintai.dev/flintai/switch](https://docs.flintai.dev/flintai/switch/index)

Follow the official instructions to install Switch Console and connect it to your collaboration tool. Ensure you have permission to create agents and rooms.

### 3.2 Agent CLI (choose at least one)

Install and authenticate **one** of the following. Each must be able to run from the cloned repository directory.

| Provider | Install (verify against official docs) | Authenticate | Official documentation |
|---|---|---|---|
| **Cursor CLI** | `curl https://cursor.com/install -fsS \| bash` | `cursor-agent login` | [cursor.com/cli](https://cursor.com/cli) |
| **Codex CLI** | `npm install -g @openai/codex` | Run `codex` and sign in | [github.com/openai/codex](https://github.com/openai/codex) |
| **Claude Code (Claude CLI)** | `npm install -g @anthropic-ai/claude-code` | Run `claude` and sign in | [docs.claude.com](https://docs.claude.com/en/docs/claude-code/overview) |

> Installation methods change over time. If a command above fails, follow the official documentation linked in the table.

### 3.3 Other requirements

- Git
- Node.js (required for the npm-based installs above)
- Product and Engineering teammates to invite to the room

## 4. Setup

### Step 1. Clone the repository

```bash
git clone https://github.com/SakaethRam/XANDER-WORKFLOW.git
cd XANDER-WORKFLOW
```

### Step 2. Confirm the CLI works from the repository

From inside the cloned folder, launch your chosen CLI (`cursor-agent`, `codex`, or `claude`) once and confirm it starts and is authenticated.

### Step 3. Import the preset into Switch Console

Once the prerequisites in [Section 3](#3-prerequisites) are in place, import the **XANDER WORKFLOW** preset into Switch Console as a **custom template**, using the preset file in [`config/`](config/).

Set the agent's **working directory** to the absolute path of your cloned folder so Xander can read `AGENTS.md`, `context/`, and `workflows/`.

> Menu names and import steps vary by Switch Console version. Refer to the [Switch documentation](https://docs.flintai.dev/flintai/switch/index) for the exact flow.

### Step 4. Apply the agent instructions

If your provider does not automatically load `AGENTS.md`, paste the prompt from [`config/agent-instructions.md`](config/agent-instructions.md) into the agent's instruction field. `AGENTS.md` remains the authoritative operating document.

### Step 5. Create the shared room and add Xander

1. Create **one** shared room for Product and Engineering. A single room lets both sides see the same conversation.
2. Add the Xander agent to the room.
3. Invite Product Managers and Engineers.

Suggested note to the team:

> *Xander is a neutral assistant that helps us understand each other. It does not make decisions. Ask it to explain, clarify, or help align, in plain language.*

### Step 6. Verify

Post the sample messages below and compare Xander's behavior with the matching workflow file and [`examples/`](examples/).

| Test message | Expected behavior |
|---|---|
| "Can we make the dashboard load instantly?" | Targeted clarifying questions; no invented targets |
| "The initial API response is slow because we're fetching too much data synchronously." | Plain-language explanation with caveats |
| "Customers are abandoning onboarding because the dashboard is slow." | Problem, outcome, and missing information; claimed cause marked unverified |
| "Xander, summarize what we've agreed on this feature." | Table separating Agreed / Proposed / Open |
| Product: "Must ship before launch." Engineering: "It depends on an unfinished rework." | Both positions and trade-offs, with no recommendation |

Also test **silence**: post a clear message such as "Standup moved to 10:30" and confirm Xander does not intervene. Additional scenarios are available in [`test-case/`](test-case/).

## 5. Changing the Provider

The provider is controlled by a single field in the preset. To switch from one provider to another, open the preset file in [`config/`](config/) and change the `provider:` value:

```yaml
provider: cursor    # change to your preferred provider, e.g. codex or claude
```

After editing:

1. Confirm the new provider's CLI is installed and authenticated (see [Section 3.2](#32-agent-cli-choose-at-least-one)).
2. Re-import or update the preset in Switch Console.
3. Restart the agent session so the change takes effect.

> Use the provider identifier that your Switch Console version supports. The instructions in this repository do not depend on a specific model or provider.

## 6. Repository Structure

```
XANDER-WORKFLOW/
├── AGENTS.md          # Master operating instructions for Xander
├── README.md          # This file
├── config/            # Preset and agent onboarding instructions
├── context/           # Reference profiles: Product and Engineering
├── instructions/      # Role definition, tone, format, and certainty rules
├── workflows/         # The five core workflows
├── examples/          # Illustrative example conversations
└── test-case/         # Test scenarios for validating behavior
```

## 7. Core Workflows

| Workflow | Purpose |
|---|---|
| **Clarification** | Resolve ambiguity with targeted questions before work proceeds |
| **Technical-to-Business Translation** | Explain engineering concepts in plain, outcome-focused language |
| **Business-to-Technical Translation** | Convert product intent into clear, actionable technical context |
| **Requirements Alignment** | Separate what is agreed, proposed, and still open |
| **Priority Alignment** | Present both positions and trade-offs without making the decision |

## 8. Customizing Context

Edit the files in [`context/`](context/) to reflect your organization:

- Add company-specific terms (for example, what "launch", "P0", or "done" mean to your teams).
- Describe your architecture and stack in general terms.
- Update responsibilities and processes to match how your teams work.

Commit changes so every teammate's Xander setup stays consistent.

## 9. Troubleshooting

| Symptom | Things to check |
|---|---|
| Xander does not respond | Is it added to the room? Does your setup deliver all messages or only mentions? Is the provider CLI running and authenticated? |
| Xander ignores repository rules | Is the working directory set correctly? If the provider does not read `AGENTS.md`, paste `config/agent-instructions.md`. |
| Too chatty | Re-emphasize the "intervene only when it materially improves understanding" rule. |
| Too quiet | Ask explicitly (for example, "Xander, can you explain that for Product?") and check delivery settings. |
| Provider change has no effect | Confirm the `provider:` value, re-import the preset, and restart the agent session. |

## 10. Privacy and Security

- Grant the agent access only to authorized rooms and conversations.
- Content in the room may be sent to the model provider you configure. Review that provider's data handling and retention terms.
- Do not store secrets, credentials, or personal data in this repository or in `context/` files.
- Keep API keys and tokens out of version control.
- Run the agent with the least file access your setup allows.
- Review your organization's policy on third-party AI services before use.

## 11. Known Limitations

- Switch Console menu names, import steps, and mention or trigger behavior vary by version.
- Automatic monitoring of every room message depends on your Switch configuration.
- Output quality varies by provider and model.
- Xander cannot verify claims about your systems or customers; it works only with what the room provides.
- Example conversations are illustrative.
