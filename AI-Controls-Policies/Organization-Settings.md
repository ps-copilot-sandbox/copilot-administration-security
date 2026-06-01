# Demo: Organization-Level GitHub Copilot Settings

> **Audience:** GitHub Copilot Administrators
> **Goal:** Walk administrators through Copilot configuration at the organization level.

---

## Setup

Have the participant share their screen on their **Organization account** and navigate to:

```markdown
https://github.com/organizations/[ORGANIZATION]/settings/copilot/seat_management
```

From here, go to **Settings → Copilot** and walk through each section.

> **Note:** No need to show **Access** — that will be covered during the Onboarding Users demo.

---

## Copilot Settings

### Policies

Policies define what Copilot features and behaviors are permitted within the organization.

- Review toggles for features like **Copilot Memory**, **Copilot metrics API**, and **Copilot cloud agent**.
- Organization policies inherit enterprise guardrails.
- Organization admins can configure the settings that enterprise admins delegate to the organization.

---

### Models

Control which AI models are available to members of this organization.

- Show available models (e.g., GPT-4o, Claude Sonnet, Gemini).
- Explain that restricting models can address compliance requirements or standardize the developer experience.
- Model availability is subject to what the enterprise has allowed.

---

### Custom Instructions

Custom instructions let organizations provide persistent context to Copilot for all users.

- Instructions can include coding standards, preferred frameworks, or internal terminology.
- These apply automatically across Copilot Chat and inline suggestions for org members.
- Great for enforcing consistency without requiring developers to configure anything themselves.

---

### Content Exclusion

Prevent Copilot from referencing specific files or directories within repositories in this organization.

- Exclusions apply to all users in the org, regardless of individual settings.
- Common use cases: excluding secrets files, proprietary algorithms, or sensitive configuration.
- Works in combination with enterprise-level content exclusions.

---

### Cloud Agent

Configure settings for GitHub Copilot's cloud-based agent capabilities at the organization level.

- Review which repositories and workflows agents are permitted to act on.
- Discuss how cloud agents differ from locally-run coding assistants (they can take actions, open PRs, run workflows, etc.).
- Highlight the importance of scoping agent permissions carefully in a production environment.

---

### Secrets and variables

Go to **Settings → Secrets and variables → Agents** to show how organizations can manage secrets that Copilot agents can access.

- Review how to add secrets and variables at the organization level that can be used by agents in any repository within the org.

---

## Key Takeaways

- Organization settings provide a **middle layer of control** between enterprise policies and individual repository settings.
- **Custom instructions** are a powerful way to enforce standards without burdening individual developers.
- **Content exclusion** at the org level protects sensitive code across all repos without repo-by-repo configuration.