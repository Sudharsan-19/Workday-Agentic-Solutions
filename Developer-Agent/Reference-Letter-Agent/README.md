# Workday Reference Letter Agent

A custom Workday agent built with the Developer Agent (WDCLI in VS Code), deployed to a personal tenant, configured in ASOR, and exposed through MCP so it can be used from Claude and other MCP-compatible applications.

## Overview

| Item | Detail |
|------|--------|
| Built with | Workday Developer Agent via WDCLI, in Visual Studio Code |
| Deployment target | Personal Workday tenant |
| Configuration | ASOR (agent configuration and tool security) |
| Exposure | MCP (tested with Claude; external agent pushed via Postman) |
| Status | Working in personal tenant |

## Architecture

```
VS Code + WDCLI (Developer Agent)
        │  build & deploy
        ▼
Personal Workday Tenant ── Agent configured in ASOR
        │  tool security & stop gates
        ▼
Agent Gateway (ODP endpoint)
        │  MCP server
        ▼
Clients: Postman (testing) → Claude / other MCP apps
```

See `AGENT_DEFINITION.md` for the agent's full configuration and `AGENT_SKILLS.md` for the skills it exposes.

## Prerequisites

- Access to a Workday personal tenant
- Visual Studio Code with WDCLI installed
- Access to the Workday Developer Agent
- Postman (for testing the MCP endpoint)
- An MCP-compatible client, such as Claude, for end-to-end testing

## Setup Steps

1. **Authenticate first.** Log in to your tenant through the WDCLI before using the Developer Agent.
2. **Build the agent** in VS Code using the Developer Agent.
3. **Deploy to your personal tenant.**
4. **Configure the agent in ASOR.**
5. **Set up tool security.** Define which tools the agent can use and the permissions for each.
6. **Add stop gates** in tool permissions to require approval before sensitive actions run.
7. **Test the MCP endpoint in Postman** to confirm the agent and its tools respond.
8. **Connect a client.** Add a custom MCP connector in Claude (or another MCP app). The gateway should list the agent's tools.

## Lessons Learned

- **Authenticate through the CLI before the Developer Agent.** The Developer Agent could not authenticate correctly at first, which caused several access fallbacks. Logging in through WDCLI first resolved this.
- **Personal tenants use ODP gateway endpoints.** If authentication or the connection breaks without an obvious cause, check the gateway endpoint and point it to ODP. Workday updated personal tenant gateways to ODP during a weekly maintenance window; earlier setups referred to US gateways.
- **Stop gates belong in tool permissions.** Gating tools this way lets you control which actions run automatically and which need review.
- **Tools that need WIDs must receive them.** If a tool requires specific WIDs, pass them through the agent skill or a custom agent action so the agent can reference them.
- **Use the MCP vs A2A decision matrix** (below) to choose the invocation channel before building.

## Invocation Channel Decision Matrix (MCP vs A2A)

*Starting framework. Adjust the criteria to your organization's needs, budget, and architecture.*

| Criterion | Prefer MCP when… | Prefer A2A when… |
|-----------|------------------|------------------|
| Client type | A single assistant or app (e.g., Claude) needs direct tool access | Multiple agents need to coordinate and hand off work |
| Interaction style | Tool calls with clear inputs and outputs | Multi-step, conversational task delegation |
| Governance | Tool-level permissions and stop gates are the main control | Agent-level trust and orchestration are needed |
| Cost and invocation volume | Low-volume, on-demand calls | Frequent agent-to-agent calls where reducing developer agent invocations matters |
| Architecture | Simple integration with an existing MCP client | Distributed or multi-agent architecture |

## Files in This Folder

| File | Purpose |
|------|---------|
| `README.md` | This file: overview, setup, lessons learned |
| `AGENT_DEFINITION.md` | Agent identity, configuration, tools, and permissions |
| `AGENT_SKILLS.md` | Skills, triggers, steps, and WID dependencies |

## Status and Next Steps

- [x] Agent built and deployed to personal tenant
- [x] Configured in ASOR
- [x] Tool security and stop gates set up
- [x] Exposed through MCP and tested with Claude
- [ ] Add a worked example request and response
- [ ] Publish reference letter sample output (synthetic data only)
