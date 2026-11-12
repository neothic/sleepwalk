<p align="center">
  <img src=".github/icon.png" width="160" height="160" alt="Sleepwalk icon">
</p>

<h1 align="center">Sleepwalk</h1>

<h3 align="center">Leave the office. Your Mac keeps working.</h3>

<p align="center">
  Close the lid, put your Mac in your backpack and turn on your iPhone’s hotspot.<br>
  Sleepwalk keeps the Mac awake and online.
</p>

<p align="center">
  <a href="https://github.com/neothic/sleepwalk/releases/latest"><b>Download for Mac</b></a><br>
  <sub>Free · macOS 14 or later</sub>
</p>

---

## How it works

1. **Start a session** from the menu bar.
2. **Close the lid.** The Mac stays awake.
3. **Turn on Personal Hotspot** on your iPhone. Sleepwalk keeps the Mac connected to it.

Useful for AI coding agents on the commute, long builds and test runs, and uploads.

## Features

- Awake with the lid closed
- Reconnects to your iPhone’s hotspot
- Stays on the hotspot instead of other Wi-Fi
- Remote desktop and screen recording with the lid closed
- Mute, dim and lock on lid close
- Low Power Mode with the lid closed
- Session end on low battery or heat
- Session history
- Keyboard shortcut, Siri, Spotlight and command line

## Setup

### With AI

Paste this into Claude Code or Codex, or open it in [Cursor](https://cursor.com/link/prompt?text=Install%20Sleepwalk%20%28https%3A%2F%2Fgithub.com%2Fneothic%2Fsleepwalk%29%20on%20this%20Mac%2C%20connect%20yourself%20to%20it%20and%20set%20it%20up.%0A%0A1.%20Download%20the%20.zip%20from%20the%20latest%20release%20at%20https%3A%2F%2Fgithub.com%2Fneothic%2Fsleepwalk%2Freleases%2Flatest%20and%20unpack%20it%20with%20%60ditto%20-x%20-k%60.%0A2.%20Check%20it%20before%20installing%3A%20%60spctl%20--assess%20--type%20execute%20-v%20Sleepwalk.app%60%20must%20report%20%22Notarized%20Developer%20ID%22%2C%20and%20%60codesign%20-dv%20Sleepwalk.app%60%20must%20show%20TeamIdentifier%3D2H5DY5334C.%20Stop%20if%20either%20differs.%0A3.%20Move%20Sleepwalk.app%20to%20%2FApplications%20and%20open%20it.%0A4.%20Add%20its%20MCP%20server%20to%20your%20own%20configuration%2C%20for%20every%20project.%20The%20server%20command%20is%20%60%2FApplications%2FSleepwalk.app%2FContents%2FMacOS%2FSleepwalk%20mcp%60.%0A5.%20Ask%20me%20for%20my%20iPhone%20hotspot%27s%20name%20and%20password%2C%20and%20set%20them%20with%20that%20same%20command%3A%20%60set%20hotspot%20%3Cname%3E%60%20and%20%60set%20hotspot-password%20%3Cpassword%3E%60.%20iPhone%20hotspot%20names%20use%20%E2%80%99%2C%20not%20%27.%0A6.%20Run%20%60grant-permission%60%20and%20tell%20me%20macOS%20will%20ask%20for%20my%20Mac%20password.%0A7.%20Run%20%60status%60%20and%20tell%20me%20if%20anything%20is%20left.).

```text
Install Sleepwalk (https://github.com/neothic/sleepwalk) on this Mac, connect yourself to it and set it up.

1. Download the .zip from the latest release at https://github.com/neothic/sleepwalk/releases/latest and unpack it with `ditto -x -k`.
2. Check it before installing: `spctl --assess --type execute -v Sleepwalk.app` must report "Notarized Developer ID", and `codesign -dv Sleepwalk.app` must show TeamIdentifier=2H5DY5334C. Stop if either differs.
3. Move Sleepwalk.app to /Applications and open it.
4. Add its MCP server to your own configuration, for every project. The server command is `/Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk mcp`.
5. Ask me for my iPhone hotspot's name and password, and set them with that same command: `set hotspot <name>` and `set hotspot-password <password>`. iPhone hotspot names use ’, not '.
6. Run `grant-permission` and tell me macOS will ask for my Mac password.
7. Run `status` and tell me if anything is left.
```

### Manual

1. [Download Sleepwalk](https://github.com/neothic/sleepwalk/releases/latest), move it to Applications and open it.
2. In **Settings → Hotspot**, enter the hotspot name and password.
3. In **Settings → General**, click **Grant**.

## AI connector

Sleepwalk is an MCP server, so an AI app can start and end sessions itself.

Connect Claude, Cursor or Visual Studio Code in **Settings → AI Apps**.

<details>
<summary>Claude Code, Codex and other apps</summary>

**Claude Code**

```
claude mcp add --scope user sleepwalk -- /Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk mcp
```

**Codex**

```
codex mcp add sleepwalk -- /Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk mcp
```

**Any other app**

```json
{
  "mcpServers": {
    "sleepwalk": { "command": "/Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk", "args": ["mcp"] }
  }
}
```
</details>

## Questions

**Is it safe to keep a closed Mac in a bag?**

It can get hot. Sleepwalk ends the session when macOS reports heat, but it can’t prevent overheating, so leave some airflow around your Mac.

**Why does it ask for an administrator password?**

Keeping a closed Mac awake is a system setting, and changing it needs an administrator. Sleepwalk asks once.

**How do I remove it?**

Settings → General → Uninstall.

## Feedback

Found a bug or missing something?
[Open an issue](https://github.com/neothic/sleepwalk/issues/new).

---

<p align="center">
  <sub>This repository holds releases only. Use of Sleepwalk is subject to the <a href="LICENSE">licence</a>.<br>© <a href="https://neothic.com">Neothic d.o.o.</a></sub>
</p>
