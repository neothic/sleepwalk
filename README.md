<p align="center">
  <img src=".github/icon.png" width="160" height="160" alt="Sleepwalk icon">
</p>

<h1 align="center">Sleepwalk</h1>

<h3 align="center">Leave the office. Your Mac keeps working.</h3>

<p align="center">
  Close the lid, put your Mac in your backpack and turn on your iPhone’s hotspot.<br>
  Sleepwalk keeps the Mac awake and joins the hotspot every time the Wi-Fi drops.
</p>

<p align="center">
  <a href="https://github.com/neothic/sleepwalk/releases/latest"><b>Download for Mac</b></a><br>
  <sub>Free · macOS 14 or later</sub>
</p>

---

## How it works

1. **Start a session** from the menu bar, for a set time or until you end it.
2. **Close the lid.** The Mac stays awake, mutes, darkens and locks.
3. **Turn on Personal Hotspot** on your iPhone. The Mac joins it, and joins
   again whenever the connection drops.

Ending the session puts every setting back.

People use it for AI coding agents left running on the commute, for long
builds and test runs, and for uploads that would otherwise stop at the door.

## Setup

1. [Download Sleepwalk](https://github.com/neothic/sleepwalk/releases/latest),
   move it to Applications and open it.
2. In **Settings → Hotspot**, enter the hotspot name and password. If the Mac
   is on the hotspot already, click **Use Current**.
3. In **Settings → General**, click **Grant**.

Sleepwalk updates itself.

### Or let your AI agent install it

Copy this into Claude Code, Codex or any agent with a terminal, or
[open it in Cursor](https://cursor.com/link/prompt?text=Install%20Sleepwalk%20%28https%3A%2F%2Fgithub.com%2Fneothic%2Fsleepwalk%29%20on%20this%20Mac%20and%20connect%20yourself%20to%20it.%0A%0A1.%20Download%20the%20.zip%20from%20the%20latest%20release%20at%20https%3A%2F%2Fgithub.com%2Fneothic%2Fsleepwalk%2Freleases%2Flatest%20and%20unpack%20it%20with%20%60ditto%20-x%20-k%60.%0A2.%20Check%20it%20before%20installing%3A%20%60spctl%20--assess%20--type%20execute%20-v%20Sleepwalk.app%60%20must%20report%20%22Notarized%20Developer%20ID%22%2C%20and%20%60codesign%20-dv%20Sleepwalk.app%60%20must%20show%20TeamIdentifier%3D2H5DY5334C.%20Stop%20if%20either%20differs.%0A3.%20Move%20Sleepwalk.app%20to%20%2FApplications%20and%20open%20it.%0A4.%20Add%20its%20MCP%20server%20to%20your%20own%20configuration%2C%20for%20every%20project.%20The%20server%20command%20is%20%60%2FApplications%2FSleepwalk.app%2FContents%2FMacOS%2FSleepwalk%20mcp%60.%0A5.%20Tell%20me%20to%20finish%20in%20Sleepwalk%27s%20Settings%3A%20the%20hotspot%20name%20and%20password%20under%20Hotspot%2C%20and%20Grant%20under%20General.%20Those%20two%20are%20mine%20to%20do.). The agent downloads Sleepwalk, checks it, installs
it and connects itself. The hotspot and the permission stay yours to set.

```text
Install Sleepwalk (https://github.com/neothic/sleepwalk) on this Mac and connect yourself to it.

1. Download the .zip from the latest release at https://github.com/neothic/sleepwalk/releases/latest and unpack it with `ditto -x -k`.
2. Check it before installing: `spctl --assess --type execute -v Sleepwalk.app` must report "Notarized Developer ID", and `codesign -dv Sleepwalk.app` must show TeamIdentifier=2H5DY5334C. Stop if either differs.
3. Move Sleepwalk.app to /Applications and open it.
4. Add its MCP server to your own configuration, for every project. The server command is `/Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk mcp`.
5. Tell me to finish in Sleepwalk's Settings: the hotspot name and password under Hotspot, and Grant under General. Those two are mine to do.
```

## AI apps

A connected AI app starts a session before a long task and ends it when the
task is done.

Open **Settings → AI Apps** and click **Connect** next to Claude, Cursor or
Visual Studio Code. The app asks you to confirm, and that is all.

An AI app can start and end sessions, read the status and history, and change
how a session behaves. The safeguards, the screen lock and the hotspot stay
yours, and the hotspot password never passes through an AI app.

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

**Any other app:** Sleepwalk is an [MCP](https://modelcontextprotocol.io)
server. In the app’s MCP settings:

```json
{
  "mcpServers": {
    "sleepwalk": { "command": "/Applications/Sleepwalk.app/Contents/MacOS/Sleepwalk", "args": ["mcp"] }
  }
}
```
</details>

## Features

- **Awake with the lid closed**, from 5 minutes to 24 hours, or until you end
  the session.
- **Hotspot.** While the Mac is offline, Sleepwalk tries to join your hotspot
  every 5 seconds. The password is kept in your keychain.
- **Stay on Hotspot.** On the way out you pass Wi-Fi the Mac knows, and macOS
  hops onto each one. Stay on Hotspot keeps the Mac on your hotspot for the
  whole session.
- **Low Power Mode** during a session, so the Mac stays cooler in a bag.
- **Mute, darken, lock** when the lid closes. Each is a setting of its own.
- **Low battery and heat.** A session ends at 10% battery and when macOS
  reports the Mac hot. Both levels are yours to set.
- **Session history.** Each session has a timeline of lid changes, networks
  joined and time offline.
- **Settings restored.** However a session ends, it puts back what it changed.
- **Shortcut, Siri, command line.** ⌃⌥⌘W starts or ends a session from any
  app. Shortcuts, Spotlight and Siri have the same actions, and so does
  `sleepwalk` in Terminal, after **Settings → General → Install**.

## Questions

**Is it safe to keep a closed Mac in a bag?**
It can get hot. Sleepwalk runs the Mac in Low Power Mode and ends the session
when macOS reports heat, but it can’t prevent overheating, so leave some
airflow around your Mac.

**Why does it ask for an administrator password?**
Keeping a Mac awake with the lid closed and switching Low Power Mode are
system settings, and changing them needs an administrator. Sleepwalk asks
once, when you click Grant.

**How do I remove it?**
Settings → General → Uninstall removes the app and everything it keeps on
your Mac.

## Feedback

Found a bug or missing something?
[Open an issue](https://github.com/neothic/sleepwalk/issues/new).

---

<p align="center">
  <sub>This repository holds releases only. Use of Sleepwalk is subject to the <a href="LICENSE">licence</a>.<br>© <a href="https://neothic.com">Neothic d.o.o.</a></sub>
</p>
