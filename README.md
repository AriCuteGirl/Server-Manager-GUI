<p align="center"><img src="icon.png" width="128" alt=""></p>

<h1 align="center">Server Manager</h1>

<p align="center">A desktop app that sets up and manages private servers of revived games.<br>
Linux and Windows. Free.</p>

<p align="center"><a href="https://github.com/AriCuteGirl/Server-Manager-GUI/releases/latest"><b>⬇ Download the newest version</b></a></p>

---

Some old games lost their online servers. Fans wrote new servers for them
("server emulators"). **Server Manager** makes running such a server easy,
without the command line:

- **Set up** a server on your own PC or on a VPS (Oracle Cloud free tier,
  Hetzner, AWS or any Linux server), step by step.
- A **firewall checklist** for your provider, with values you can copy.
- **Deploy** with one click, then a check that players can reach it from the internet.
- **Manage:** status, start / stop / restart, live log, players (change money,
  tickets, level), settings, promo codes, backups, and moving to another server.
- Dark and light theme.

## Games

| Game | Platform | Server project |
|---|---|---|
| Theme Park (EA, 2012) | Android | [Theme-park-EA-Server](https://github.com/AriCuteGirl/Theme-park-EA-Server) |
| Surgeon Simulator 2 (1.5.1 co-op) | PC (Steam) | [SurgeonSim2-Private-Server](https://github.com/AriCuteGirl/SurgeonSim2-Private-Server) |

You need your own copy of the game. Server Manager doesn't include any game files.

## Download

Go to [Releases](https://github.com/AriCuteGirl/Server-Manager-GUI/releases/latest) and pick one:

| File | For |
|---|---|
| `Server-Manager-<version>-x86_64.AppImage` | Linux (any distro, 64-bit) |
| `Server-Manager-Setup-<version>.exe` | Windows 10/11 installer |
| `Server-Manager-<version>-portable.exe` | Windows, no installing, just run it |

### Linux

```bash
chmod +x Server-Manager-*.AppImage
./Server-Manager-*.AppImage
```

If it doesn't start, install FUSE 2 (Arch: `sudo pacman -S fuse2`,
Ubuntu: `sudo apt install libfuse2`).

### Windows

Run the installer. Windows may show "Windows protected your PC" because the app
is not signed yet: click **More info → Run anyway**.

## What you need

- **For a VPS:** a Linux server with SSH, Python 3.9 or newer, and a user with
  `sudo` (Oracle and most cloud images have all of this). You log in with an SSH
  key file.
- **For this PC:** Python 3 (on Windows from [python.org](https://www.python.org/downloads/),
  tick "Add to PATH").

## Safe by design

- Everything goes over **SSH**. The app opens no extra ports on your server.
- It saves only the **path** to your SSH key, never the key or a password.
  Saved servers are encrypted with your system keychain.
- The first time you connect, you confirm the server's fingerprint. If it ever
  changes, the app refuses to connect.
- Anything that changes your server asks you first.

## Check your download (optional)

Each release has a `SHA256SUMS.txt`:

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```

## Problems or ideas?

Open an [issue](https://github.com/AriCuteGirl/Server-Manager-GUI/issues).

---

Made by Ari. This repository only has the built app; the source code is private.
