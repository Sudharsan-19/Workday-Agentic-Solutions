# Workday Agentic Solutions

A public collection of agentic solutions I build on the Workday platform: agent definitions, skills, deployment notes, and lessons learned from working with Workday's agent tooling.

Each solution is documented in its own folder so it can be read, reused, or adapted independently.

## Repository Structure

```
Workday-Agentic-Solutions/
├── README.md                              # This file
├── Developer-Agent/                       # Examples of Workday Developer Agent solutions
│   ├── README.md                          # Index of Developer Agent examples
│   └── Workday-Reference-Letter-Agent/
│       ├── README.md                      # Overview, setup, and lessons learned
│       ├── AGENT_DEFINITION.md            # What the agent is and how it is configured
│       └── AGENT_SKILLS.md                # Skills the agent exposes and how they run
└── Sana/                                  # Reserved for Sana solutions (empty for now)
```

## Solution Index

| Area | Solution | Status | Docs |
|------|----------|--------|------|
| Developer Agent | Workday Reference Letter Agent | Active | [README](Developer-Agent/Workday-Reference-Letter-Agent/README.md) |
| Sana | Reserved for future solutions | Empty | — |

## How Each Solution Is Organized

Every agent solution follows the same three-file pattern so readers know where to look:

- **README.md**: What the solution does, architecture, prerequisites, setup steps, and lessons learned.
- **AGENT_DEFINITION.md**: The agent's identity, purpose, inputs and outputs, tools, permissions, and invocation channels.
- **AGENT_SKILLS.md**: The skills the agent exposes, with triggers, steps, required tools, and WID dependencies.

## Conventions

- **No tenant data.** Tenant URLs, gateway endpoints, credentials, tokens, and real Workday IDs (WIDs) are never committed. Use placeholders such as `<TENANT_URL>` and `<WID_EXAMPLE>`.
- **Personal tenant disclaimer.** Examples are built and tested in personal Workday tenants. They are not production guidance and do not represent Workday's official products or recommendations.
- **Lessons learned are included.** Where a setup step caused friction, the solution's README documents the fix.

## Disclaimer

These are independent, personal projects. They are not affiliated with or endorsed by Workday. Platform features and endpoints may change; always verify against current Workday documentation.

## License

[Add license, e.g., MIT]
