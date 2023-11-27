# Visual Studio Code

## Logs stored in Standard Location for Visual Studio Code Extensions
 - View -> Output -> GitHub Copilot - VS Code Command Palette -> Developer: Open Extension Logs Folder
Network Connectivity Diagnostic Logs, due to network restrictions, firewalls, or your proxy setup - VS Code Command Palette -> GitHub Copilot: Copilot Diagnostics - Check Reachability, access the necessary services - Certification error, check `Custom Certificates:`. If disabled, cannot use CfB, as custom certificates are not supported
Enable Debug Mode - Log files doesn't contain enough information to resolve the issue - Temporarily enable debug logging - Disable the Custom Debug Log Configuration

- VS Code Command Palette -> Preferences: Open User Settings (JSON) -> Insert top-level property, then save "github.copilot.advanced": { "debug.overrideLogLevels": { "*": "DEBUG" } },
Viewing Electron Logs - Rare cases, errors might not be propagated to the corresponding error handlers and are not logged in the regular locations - Encounter errors and nothing in logs - Logs from the process running VS Code & the extension

- VS Code Command Palette -> Developer: Toggle Developer Tools -> Developer Tools Window -> Console
