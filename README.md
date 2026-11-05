# Workday Agentic Solutions

This repository showcases a collection of agentic solutions I've built on the Workday platform. It includes agent definitions, custom skills, deployment guidance, implementation notes, and lessons learned from hands-on experience with Workday's agent tooling.

Each project is documented in its own folder so it can be understood, reused, or adapted independently.

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
    ├── README.md                          # Index of Sana examples
```

## Solution Index

| Area | Solution | Status | Docs |
|------|----------|--------|------|
| Developer Agent | Reference Letter Agent | Active | [README](Developer-Agent/Reference-Letter-Agent/README.md) |
| Sana | Coming Soon | Empty | — |

## How Each Solution Is Organized

Every agent solution follows the same three-file pattern so readers know where to look:

- **README.md**: What the solution does, architecture, prerequisites, setup steps, and lessons learned.
- **AGENT_DEFINITION.md**: The agent's identity, purpose, inputs and outputs, tools, permissions, and invocation channels.
- **AGENT_SKILLS.md**: The skills the agent exposes, with triggers, steps, required tools, and WID dependencies.

## Conventions

- **No tenant data.** Tenant URLs, gateway endpoints, credentials, tokens, and real Workday IDs (WIDs) are never committed. Use placeholders such as `<TENANT_URL>` and `<WID>`.
- **Personal tenant disclaimer.** Examples are built and tested in personal Workday tenants. They are not production guidance and do not represent Workday's official products or recommendations.
- **Lessons learned are included.** Where a setup step caused friction, the solution's README documents the fix.

## Disclaimer

These projects are independent personal initiatives and are not affiliated with, endorsed by, or supported by Workday, its partners, or its customers.

Workday platform features, APIs, and endpoints may change over time. Always refer to the official Workday documentation for the most current and accurate information.

