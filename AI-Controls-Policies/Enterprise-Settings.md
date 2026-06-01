# Demo: Enterprise-Level GitHub Copilot Settings

> **Audience:** GitHub Copilot Administrators <br>
> **Goal:** Walk administrators through enterprise-wide AI controls and governance settings.

---

## Setup

Have the participant share their screen on their **Enterprise account** and navigate to:

```markdown
https://github.com/enterprises/[ENTERPRISE]/ai-controls/agents
```

From here, walk through the **AI Controls** tab from top to bottom, starting with **Agents** and ending with **MCP**.

---

## AI Controls

### Agents

This section governs how AI agents behave across the enterprise.

- **Enterprise-Provided Configuration** — Review enterprise-level agent configuration provided by GitHub.
- **Configuration Source** — Select the organization that provides enterprise-managed settings, plugins, and custom agents.
- **Configuration Summary** — Summarize the effective configuration applied at the enterprise level.
- **Agent Sessions** — View and manage active Copilot agent sessions running in the enterprise. Useful for auditing ongoing activity.
- **Available Agents** — Review which Copilot agents are enabled. Admins can control which agents are accessible to users.
- **Partner Agents** — Third-party agents integrated with GitHub Copilot. Show how to enable or restrict partner-built agents.
- **Custom Agents** — Enterprise-built agents using the GitHub Copilot Extensions framework. Highlight how organizations can publish internal agents.
- **Ruleset** — Define policies that govern agent behavior, such as restricting agents to specific repositories or workflows.

> **Note:** No need to show **Audit Logs** here — that will be covered in the Telemetry demo.

---

## Copilot

> **Note:** No need to show **Access Management** here — that will be covered during the Onboarding Users demo.

- **Content Exclusion** — Prevent Copilot from accessing specific files, directories, or repositories across the entire enterprise. This is a key data governance control.
- **Configure Allowed Models** — Restrict which AI models (e.g., GPT-4o, Claude, Gemini) are available to users. Useful for compliance and cost control.
- **Privacy** — Review data handling settings, including whether Copilot suggestions are used to train GitHub's AI models. Enterprise accounts have this disabled by default.
- **Features** — Toggle specific Copilot features on or off enterprise-wide (e.g., Copilot Chat, code completion, Copilot in the CLI).
- **Billing** — Review seat usage and costs. Show how to monitor consumption at the enterprise level.
- **Metrics** — High-level usage and adoption metrics across all organizations in the enterprise. Discuss how admins can track ROI and engagement.
- **Copilot Clients** — View and manage which clients (VS Code, JetBrains, GitHub.com, CLI, etc.) are permitted to use Copilot.

---

## MCP (Model Context Protocol)

MCP allows Copilot to connect to external tools and data sources.

- **Allow / Disable** — Toggle MCP access on or off for the enterprise. Discuss security considerations before enabling.
- **Registry URL** — Configure a private MCP server registry. Useful for enterprises that want to control which MCP tools are available to developers.

---

## Key Takeaways

- Enterprise settings are the **highest level of control** — they cascade down to organizations and repositories.
- Admins can use **content exclusion**, **model restrictions**, and **agent rulesets** to enforce company-wide AI governance.
- **MCP** and **custom agents** enable extensibility while controls ensure security boundaries are maintained.
