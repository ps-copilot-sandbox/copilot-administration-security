# Demo: GitHub Copilot Troubleshooting and Diagnostics

> **Audience:** GitHub Copilot Administrators
> **Goal:** Walk administrators through practical troubleshooting steps, diagnostic log collection, and escalation paths for Copilot issues.

---

## Setup

Have the participant share their screen and keep Visual Studio Code open while testing each troubleshooting path.

---

## GitHub Status Check

Start by confirming service availability:

- Open `https://www.githubstatus.com/`
- Verify the operational status of GitHub Copilot services
- Discuss how incidents on the status page can explain widespread or transient failures

---

## Visual Studio Code Application Logs

Review standard Copilot extension logs:

- Open Visual Studio Code
- Select **View → Output**
- In the Output panel, choose **GitHub Copilot** from the dropdown
- Review log entries for authentication, network, or completion errors

---

## Command Palette Diagnostics

Open the Command Palette:

- Windows/Linux: **Ctrl+Shift+P**
- macOS: **Cmd+Shift+P**
- Or use **View → Command Palette**

Demonstrate these commands:

- **Developer: Open Extension Logs Folder**: Opens extension log files for deeper analysis
- **Copilot: Open Logs**: Opens Copilot logs directly
- **GitHub Copilot: Copilot Diagnostics**: Generates a diagnostics file for troubleshooting

---

## Enable Debug Logging

Collect more detailed logs when standard logs are insufficient:

- Open Command Palette and run **Preferences: Open User Settings (JSON)**
- Add the following configuration:

```json
"github.copilot.advanced": {
  "debug.overrideLogLevels": {
    "*": "DEBUG"
  }
}
```

- Save settings to activate debug logging

---

## Developer Tools (Electron Logs)

Use Electron logs for rare cases not visible in extension logs:

- Open Command Palette
- Run **Developer: Toggle Developer Tools**
- Review console output for renderer or process-level errors

---

## Community Support and Escalation

If issues persist after diagnostics:

- Open Copilot Community Discussions
- Share relevant logs and diagnostics details when requesting help
- Reference: Copilot Community Discussions

---

## Key Takeaways

- Always begin with service health validation before deep local troubleshooting.
- Copilot output logs, diagnostics, and debug logging provide layered insight for root-cause analysis.
- Developer Tools and community escalation are useful when issues are not resolved through standard logs.