# sftp-dss sync extension for VS Code

This version is a forked and updated version of the SFTP Plugin from [@Natizyskunk](https://github.com/Natizyskunk/).

I used the current master as a baseline to add new functionality. It extends the extension with mutliple Options.

**The first config Option:**

 `"useIgnoreForUpload": [bool]`

This allows the Ignore List to be used when uploading files via command or on Save.
No blocked files are uploaded to the server anymore
**NEW: The delete Option always bypasses the ignore List! ->** Deleting files on the server doenst follow the blocklist

It also adds a new config option for showing synced files status (its fully customizeable)

```json



 "syncStatus": {
        "type": "object",
        "description": "File sync status decoration settings. Shows visual indicators for files that are out of sync with remote.",
        "properties": {
          "enabled": {
            "type": "boolean",
            "description": "Enable file sync status decorations in the file explorer.",
            "default": false
          },
          "refreshInterval": {
            "type": "number",
            "description": "How often to refresh sync status (in milliseconds).",
            "default": 30000
          },
          "showLocalOnly": {
            "type": "boolean",
            "description": "Show indicator for files that exist only locally (not uploaded).",
            "default": true
          },
          "showRemoteOnly": {
            "type": "boolean",
            "description": "Show indicator for files that exist only on remote (not downloaded).",
            "default": true
          },
          "showModified": {
            "type": "boolean",
            "description": "Show indicator for files that are modified and out of sync.",
            "default": true
          },
          "showSynced": {
            "type": "boolean",
            "description": "Show indicator for files that are in sync.",
            "default": false
          },
          "showIgnored": {
            "type": "boolean",
            "description": "Show indicator for files that are ignored.",
            "default": false
          },
          "timeTolerance": {
            "type": "number",
            "description": "Time difference tolerance in milliseconds for date-only timestamps (when server returns 00:00:00). Files with precise timestamps (HH:MM:SS) use 60 second (1 minute) tolerance automatically. Default is 86400000 (24 hours) for FTP servers that truncate old file timestamps.",
            "default": 86400000
          }
        }
      },
```

## Installation

### Method 1 (Recommended : Auto update)

1. Select Extensions (Ctrl + Shift + X).
2. Uninstall current sftp extension from [@Natizyskunk](https://github.com/Natizyskunk/).
3. Install new extension directly from VS Code Marketplace
4. Voila
