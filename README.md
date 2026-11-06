# Product–Engineering Clarity

A portable **instruction and workflow preset** for an AI generalist agent called **Clarity**, which sits in a shared [Switch Console](#2-how-it-works) room and helps Product Management and Engineering understand each other.

> **Status:** v1.0.0, documentation-only. This repository is not a messaging application, a backend, or an AI model. Switch-specific UI steps below are described generically because they vary by version and have not been verified against official Switch documentation. See [Known limitations](#20-known-limitations).

---

## 1. What this is

Product–Engineering Clarity is a reusable AI communication layer. You point a compatible agent at this repository, add it to one shared room, and it follows the instructions in [`AGENTS.md`](AGENTS.md) to translate **meaning and implications** — not just words — between Product and Engineering.

Clarity is a neutral intermediary. It is **not** a coding assistant, project manager, generic chatbot, or decision-maker.

## 2. How it works

Three components:

1. **Switch Console** — the communication infrastructure that connects people and AI agents through shared rooms.
2. **Clarity (AI generalist agent)** — runs on a provider you configure (e.g. OpenCode with Gemini, or Codex).
3. **This repository** — the agent's working directory, containing its permanent instructions, context, and workflows.

```
 Product ─┐                       ┌─ reads AGENTS.md, context/, workflows/
          ├─►  Switch room  ◄────►│  Clarity (agent provider of your choice)
 Engineers┘ product-engineering-clarity   working directory = this repo
```

## 3. The problem it solves

Product knows customers, priorities, and outcomes. Engineering knows feasibility, architecture, and constraints. Different vocabularies lead to ambiguous requirements, repeated clarification, misread explanations, unrealistic expectations, conflicting priorities, and lost time. Clarity reduces that friction by clarifying, translating, and surfacing trade-offs, while leaving all decisions to people.

## 4. Repository structure

```
product-engineering-clarity/
├── AGENTS.md                        # Master operating instructions for Clarity
├── README.md                        # This file
├── config/
│   ├── agent-instructions.md        # Onboarding prompt to paste into the agent config
│   └── preset.yaml                  # Project-specific manifest (NOT a Switch schema)
├── context/
│   ├── product-team.md              # General reference profile: Product
│   └── engineering-team.md          # General reference profile: Engineering
├── instructions/
│   ├── generalist-role.md           # Clarity's identity, responsibilities, boundaries
│   └── communication-rules.md       # Tone, format, certainty labels
├── workflows/
│   ├── clarify.md                   # 1. Clarification
│   ├── technical-to-business.md     # 2. Technical-to-Business Translation
│   ├── business-to-technical.md     # 3. Business-to-Technical Translation
│   ├── requirements-alignment.md    # 4. Requirements Alignment
│   └── priority-alignment.md        # 5. Priority Alignment
└── examples/
    ├── 01-ambiguous-product-request.md
    ├── 02-technical-explanation.md
    └── 03-priority-disagreement.md
```

## 5. Prerequisites

- Access to Switch Console and permission to create or configure agents and rooms.
- Git.
- An account/credentials for at least one compatible agent provider (Codex, or OpenCode plus a Gemini API key).
- Product and Engineering teammates who will be invited to the room.

## 6. Clone the repository

```bash
git clone <your-repository-url> product-engineering-clarity
```

Replace `<your-repository-url>` with the URL where you host this repository.

## 7. Configure Codex as the agent provider

1. Install and authenticate Codex by following **OpenAI's official Codex documentation** for your operating system. Installation commands change, so none are reproduced here.
2. Confirm Codex can run from the cloned repository directory.
3. Make sure Switch Console can launch or connect to it according to Switch's documentation for supported agent providers.

## 8. Configure OpenCode with Gemini (free-tier alternative)

1. Install OpenCode following **OpenCode's official documentation** for your operating system.
2. Create a Gemini API key through Google's official process and configure OpenCode to use it, following OpenCode's provider-configuration documentation.
3. Confirm OpenCode runs from the cloned repository directory.
4. Connect it to Switch Console as in step 10 below.

> **Free-tier warning:** Gemini free-tier availability, quotas, and rate limits are subject to Google's current terms and may change. Do **not** assume free-tier data handling is suitable for confidential company information. Review Google's current terms before sending any internal or customer data. See [Privacy and security](#19-privacy-and-security-considerations).

## 9. Provider independence

The instructions here do not depend on a specific model or provider. Any agent that can (a) use a working directory, (b) read instruction files such as `AGENTS.md`, and (c) take part in a Switch room can use this preset. Whether a given provider auto-loads `AGENTS.md` should be checked in that provider's documentation; the onboarding prompt in step 12 covers the case where it does not.

## 10. Configure the agent in Switch Console

In Switch Console, create or register a new agent using the provider you set up (Codex or OpenCode). Name it **Clarity**. Exact menu names and steps vary by Switch version, so consult Switch's official documentation for how to add an agent; this guide does not assume particular menu locations.

## 11. Set the repository as the agent's working directory

Configure the agent's working directory to the absolute path of your cloned `product-engineering-clarity` folder. This is what lets the agent read `AGENTS.md`, `context/`, and `workflows/`. If your Switch version has no such setting, start the provider from inside the repository directory instead.

## 12. Configure the agent's instructions

Open [`config/agent-instructions.md`](config/agent-instructions.md) and paste the prompt block into whichever field in your Switch/agent setup accepts agent instructions. `AGENTS.md` remains the authoritative operating document.

[`config/preset.yaml`](config/preset.yaml) is a human-readable manifest of this preset. It is **our own documented format**, not an official Switch schema, and is not read by Switch automatically unless you have verified that it is.

## 13. Create the shared room

Create **one** room named `product-engineering-clarity`. Do not create separate departmental channels at first; one shared room is what lets both sides see the same conversation.

## 14. Add the agent to the room

Add Clarity to the room using Switch's mechanism for adding agents. Whether the agent receives every message, only mentions, or only specific triggers depends on your Switch configuration. **Do not assume Clarity monitors every message** unless you have confirmed that behaviour. If it is mention-based, tell your team to mention it, or to tell it what to look at.

## 15. Invite Product and Engineering members

Invite the relevant Product Managers and Engineers to the room. Send them a short note: *"Clarity is a neutral assistant that helps us understand each other. It doesn't make decisions. You can ask it to explain, clarify, or help align, in plain language."*

## 16. Test the five workflows

Post these in the room and check the behaviour against the matching workflow file and examples.

| # | Test message | Expect | Workflow |
|---|---|---|---|
| 1 | "Can we make the dashboard load instantly?" | Targeted questions; no invented target | [clarify](workflows/clarify.md) |
| 2 | "The initial API response is slow because we're fetching too much data synchronously. We can lazy-load secondary widgets." | Plain-language explanation with caveats | [technical-to-business](workflows/technical-to-business.md) |
| 3 | "Customers are abandoning onboarding because the dashboard takes too long to load." | Problem, outcome, journey, missing info; claimed cause marked unverified | [business-to-technical](workflows/business-to-technical.md) |
| 4 | "Clarity, can you summarise what we've agreed on this feature?" | Table separating Agreed / Proposed / Open | [requirements-alignment](workflows/requirements-alignment.md) |
| 5 | Product: "Must ship before launch." Engineering: "It depends on an unfinished rework." | Both positions, trade-offs, options without a recommendation | [priority-alignment](workflows/priority-alignment.md) |

Also test **silence**: post a clear message ("Standup moved to 10:30") and confirm Clarity does not intervene. Compare with the transcripts in [`examples/`](examples/).

## 17. Customise department context

Edit [`context/product-team.md`](context/product-team.md) and [`context/engineering-team.md`](context/engineering-team.md):

- Add your own terms (e.g. what "launch", "P0", or "done" mean at your company).
- Describe your actual architecture or stack in general terms. Avoid confidential detail unless the agent's provider is approved for it.
- Update responsibilities and processes to match your teams.

Keep the "general reference profile" notes so the agent treats unlisted details as unknown. Commit changes so every teammate's Clarity setup stays consistent.

## 18. Troubleshooting

| Symptom | Things to check |
|---|---|
| Clarity doesn't respond | Is it added to the room? Does your Switch setup deliver all messages or only mentions? Is the provider running and authenticated? |
| Clarity ignores the repo rules | Working directory set correctly? Provider reads `AGENTS.md`? If not, paste [`config/agent-instructions.md`](config/agent-instructions.md). |
| Too chatty | Re-emphasise the "intervene only when it materially improves understanding" rule; check the agent isn't running every workflow. |
| Too quiet | Ask explicitly ("Clarity, can you explain that for Product?"); check delivery settings. |
| Invents targets/dates | Reinforce `AGENTS.md` section 5; try a more capable model. |
| Rate-limit errors (free tier) | See your provider's current quota terms; reduce usage or change provider. |
| Missing-file references | Verify the folder structure matches [section 4](#4-repository-structure). |

## 19. Privacy and security considerations

- Give the agent access **only to authorised rooms and conversations**.
- Anything in the room may be sent to the model provider you configure. Check that provider's data handling and retention terms.
- **Gemini free tier:** terms and data handling are set by Google and may differ from paid tiers. Don't assume it is suitable for confidential company or customer data.
- Don't put secrets, credentials, or personal data in this repository or in `context/` files.
- Keep API keys out of version control.
- The agent is instructed not to modify files unless asked. Still, run it with the least file access your setup allows.
- Review your organisation's policies on third-party AI services before use.

## 20. Known limitations

- **Not verified:** Switch Console menu names, agent-onboarding steps, trigger/mention behaviour, and whether Switch can import this repository directly. This package does not claim one-click import.
- `config/preset.yaml` is a project-specific manifest, not an official Switch schema.
- Provider installation commands are intentionally omitted; follow each tool's official documentation.
- Automatic monitoring of all room messages depends on your Switch configuration and is not guaranteed.
- Model quality varies; smaller or free-tier models may follow the rules less reliably.
- Clarity cannot verify claims about your systems or customers; it only works with what the room provides.
- Example conversations are illustrative and fictional.
