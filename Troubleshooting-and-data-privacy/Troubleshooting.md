Demonstration steps:​

- GitHub Status Page​
- Open GitHub Status Page in a web browser: https://www.githubstatus.com/
- Demonstrate how to verify the operational status of GitHub Copilot services.​

Visual Studio Code Application Logs​

- Open Visual Studio Code.​
- From the menu, select View → Output.​
- In the Output panel, select the dropdown and filter for "GitHub Copilot" to view the standard log entries.​

Visual Studio Code Command Palette​

- Open the Command Palette by pressing Ctrl+Shift+P (Windows/Linux) or Cmd+Shift+P (macOS), or via View → Command Palette.​
- Demonstrate the following commands:​
  - Developer: Open Extension Logs Folder: Opens the external log folder for deeper analysis.​
  - Copilot: Open Logs: Directly opens Copilot logs (same as Application Menu approach).​
  - GitHub Copilot: Copilot Diagnostics: Generates a diagnostic results file to aid troubleshooting.​

Enabling Debug Logging​

- In the Command Palette, type and select Preferences: Open User Settings (JSON).​
- Demonstrate adding the following JSON snippet to enable debug-level logging:​

```yaml
"github.copilot.advanced": {​
  "debug.overrideLogLevels": {​
    "*": "DEBUG"​
  }​
}​
```

- Save the settings file to activate detailed debug logging.​
- Developer Tools for Electron Logs​
- From the Command Palette, select Developer: Toggle Developer Tools.​
- Demonstrate viewing logs from the Electron process, useful in rare cases where errors aren't captured in standard logs.​

Copilot Community​

- Open Copilot Community Discussions to demonstrate how to seek additional support and share relevant log files or troubleshooting details.​
- Reference Documentation:​
  - Copilot Community Discussions​