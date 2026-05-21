# Demo: Repository-Level GitHub Copilot Settings

> **Audience:** GitHub Copilot Administrators
> **Goal:** Walk administrators through Copilot and security settings at the individual repository level.

---

## Setup

Have the participant share their screen and navigate to a repository, then go to:

```
https://github.com/[ORG]/[REPO]/settings/copilot/content_exclusion
```

From there, go to **Settings → Copilot** and walk through each section.

---

## Copilot Settings

### Content Exclusion

Exclude specific files or paths within this repository from Copilot's context.

- Uses glob patterns (e.g., `**/secrets/**`, `*.env`) to define exclusions.
- Excluded content is not sent to the AI model — important for protecting sensitive data.
- Repository-level exclusions stack with organization and enterprise exclusions.

---

### Code Review

Configure GitHub Copilot's AI-assisted code review for pull requests in this repository.

- Enable or disable automatic Copilot review comments on PRs.
- Copilot can surface potential bugs, style issues, and security concerns as review feedback.
- Review settings control when Copilot is triggered (e.g., on all PRs, or only when requested).

---

### Cloud Agent

Manage cloud agent permissions and behavior specifically for this repository.

- Define what actions agents are allowed to perform (e.g., create branches, commit code, open PRs).
- Scoping agents at the repo level gives fine-grained control over automation.

---

### Memory

Copilot Memory allows the AI to retain context about this repository across sessions.

- Stored memory can include project conventions, recurring patterns, and key architectural decisions.
- Admins can review and clear memory to ensure Copilot's context stays accurate and appropriate.

---

## Security Settings

Navigate to the **Security** section and open **Code Quality**.

### Languages

- View which programming languages are detected in this repository.
- Language detection determines which Copilot Autofix and code scanning rules apply.

### Scan Settings

- Configure code scanning behavior, including which rulesets and query suites to use.
- Admins can enable or disable specific security checks (e.g., SQL injection, XSS detection).
- Review default vs. extended query suites — extended suites catch more issues but may produce more noise.

### Scan Events

- Define when code scanning runs: on push, on pull request, on schedule, or all of the above.
- Discuss the tradeoff between shift-left security (early PR scanning) and performance impact.

---

## Agents Tab

Navigate to the **Agents** tab at the top of the repository settings.

- Review agents that have been granted access to act on this repository.
- Admins can approve, revoke, or restrict agent permissions at this level.
- Discuss how agent activity is traceable through audit logs and action history.

---

## Key Takeaways

- Repository settings provide the **most granular level of control** for Copilot and security features.
- **Content exclusion**, **memory**, and **code review** together help ensure Copilot behaves appropriately within a specific codebase.
- The **Agents tab** is critical for tracking and managing automated AI-driven activity in production repositories.

