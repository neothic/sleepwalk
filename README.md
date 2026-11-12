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

## Why Sleepwalk

Plenty of apps keep a Mac awake. Close the lid and walk to your car, though,
and the Mac loses the office Wi-Fi. It stays offline until you open it and
pick your hotspot by hand, and whatever it was running waits the whole way.

Sleepwalk picks the hotspot for you, as often as the connection drops.

## How it works

1. **Start a session** from the menu bar, for a set time or until you end it.
2. **Close the lid.** The Mac stays awake, mutes, darkens and locks.
3. **Turn on Personal Hotspot** on your iPhone. The Mac joins it.

Ending the session puts every setting back.

## Made for

- **AI coding agents** such as Claude Code or Codex, left running on the commute
- **Long builds and test runs** started before you leave the desk
- **Uploads, downloads and backups** that would otherwise stop at the door

## Features

### Awake with the lid closed
A session keeps the Mac running with the lid shut, from 5 minutes up to 24
hours, or indefinitely. The Z in the menu bar fills in while a session runs.

### Joins your hotspot
While the Mac is offline, Sleepwalk tries to join your hotspot every 5 seconds
by default, or at any interval from 2 to 60 seconds. The menu shows where it
stands: *Joining*, *Not in Range* or *Password Rejected*. The password is kept
in your keychain.

### Stay on Hotspot
On your way out you pass networks the Mac has joined before, and macOS
switches to each one. Meanwhile your iPhone stops offering its hotspot a short
while after the Mac leaves it, so when that Wi-Fi drops, the hotspot is gone
too.

Stay on Hotspot, on by default, keeps the Mac on your hotspot for the whole
session. Turn it off to let the Mac use Wi-Fi it knows; Sleepwalk goes back to
the hotspot when that Wi-Fi drops, as long as your iPhone still offers it.

### Mute, darken, lock
When the lid closes, audio mutes, the display goes dark and the screen locks.
Each is a setting of its own.

### Low battery and heat
A session ends at 10% battery, or at the level you set. It also ends when
macOS reports the Mac is hot; you choose Warm, Hot or Critical.

### Session history
Each session has a timeline of lid changes, networks joined and time offline.
Its summary gives the share of time on the hotspot, on other Wi-Fi and
offline, the number of drops and the longest one.

### Settings restored
However a session ends, it puts back what it changed, a crash included. If the
Mac restarts mid-session, Sleepwalk restores the settings the next time it
opens.

### Shortcut, Siri, command line and agents
- **⌃⌥⌘W** starts or ends a session from any app.
- **Shortcuts, Spotlight and Siri** get four actions: Start Sleepwalk Session,
  End Sleepwalk Session, Get Sleepwalk Status and Test Hotspot Connection.
- **Command line**, after Settings → General → Install:

  ```
  sleepwalk start 2h
  sleepwalk status
  sleepwalk history
  sleepwalk set stay-on-hotspot on
  ```
- **AI agents** run the same commands. Tell Claude Code or Codex to start a
  session before a long task and end it when the task is done, or put that
  in a skill so it happens every time.

## Setup

1. [Download Sleepwalk](https://github.com/neothic/sleepwalk/releases/latest),
   move it to Applications and open it.
2. In **Settings → Hotspot**, enter the hotspot name and password. If the Mac
   is on the hotspot already, click **Use Current**.
3. In **Settings → General**, click **Grant**.

Sleepwalk updates itself.

## Questions

**Is it safe to keep a closed Mac in a bag?**
It can get hot. Sleepwalk ends a session when macOS reports high temperature,
but it can’t prevent overheating, so leave some airflow around your Mac.

**Why does it ask for an administrator password?**
Keeping a Mac awake with the lid closed is a system setting, and changing it
needs an administrator. Sleepwalk asks once, when you click Grant.

**How do I remove it?**
Settings → General → Uninstall removes the app and everything it keeps on
your Mac.

---

<p align="center">
  <a href="https://github.com/neothic/sleepwalk/releases/latest"><b>Download Sleepwalk for Mac</b></a>
</p>

<p align="center">
  <sub>This repository holds releases only. Use of Sleepwalk is subject to the <a href="LICENSE">licence</a>.<br>© <a href="https://neothic.com">Neothic d.o.o.</a></sub>
</p>
