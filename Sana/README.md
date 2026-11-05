# Sana Solutions

Solutions built with the **Workday Developer Agent**, accessed through **WDCLI** inside **Visual Studio Code**. The agent helps design, build, and deploy custom Workday agents, which can then be configured in ASOR and exposed through MCP or A2A.

## Solutions

| Solution | Description | Docs |
|----------|-------------|------|
| Workday Reference Letter Agent | A custom agent that drafts Workday reference letters, deployed to a personal tenant and exposed via MCP | [Open](Workday-Reference-Letter-Agent/README.md) |

## Typical Workflow

1. Build the agent in VS Code using the Developer Agent through WDCLI.
2. Deploy to a tenant.
3. Configure the agent in ASOR.
4. Set tool permissions and stop gates.
5. Expose the agent through MCP (or A2A) to clients such as Claude.
