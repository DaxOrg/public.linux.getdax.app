# Dax for Linux

**The human harness for working with AI agents.**

The first Linux beta brings Shepherd's agent workspace and a focused set of
accelerators to Linux. Local features work without a Dax account.

## Download 0.1.0-beta.1

[Download the first beta](https://github.com/DaxOrg/public.linux.getdax.app/releases/tag/v0.1.0-beta.1)

**x86_64 / amd64 only** for this release. Debian 12+ and Ubuntu 24.04+ are the
initial package targets. Download `dax_0.1.0~beta.1_amd64.deb`, then:

```sh
sudo apt install ./dax_0.1.0~beta.1_amd64.deb
```

Open **Dax** from your application launcher, or run `dax` in a terminal.
A portable tar archive is also available; see [INSTALL.md](INSTALL.md).

## Try it

1. In **Shepherd**, choose a project folder.
2. Start a shell or select an installed coding agent: Claude Code, Codex, or Gemini CLI.
3. Open more sessions or split the current session into two panes.
4. Press **Ctrl+K** to explore Prompt Snippets, Frequent CLIs, Inject MD, Secrets,
   Ask AI / Image Ask, Image to URL, and File Drop.
5. Use **Settings** to optionally connect a Dax invite code or your OpenRouter key.

Coding agents must be installed and authenticated separately. SSH uses your normal
OpenSSH configuration; enter a host alias or `user@host`. Ports and keys can be
configured in `~/.ssh/config`.

Closing the window hides Dax and keeps sessions running. **Quit Dax** asks before
ending sessions. Terminal copy/paste uses **Ctrl+Shift+C/V**. Local prompts and
recent projects are remembered; terminal processes are not restored after quitting.

## Early beta limitations

- No full macOS feature parity yet: screen markup, background removal, image
  generation, multiplayer, and custom cloud storage are not included.
- X11 and a private Secret Service are covered by automated desktop tests.
  Interactive GNOME/KDE/Wayland testing is still needed. Screenshot and global
  shortcut portals depend on your desktop. Bind `dax --launcher` in your desktop's
  keyboard settings if automatic registration is unavailable.
- The global shortcut is enabled per running session from Settings. Its X11
  default is Ctrl+Alt+Space. A tray extension may be needed on GNOME; the application
  launcher works without one.
- AI requires a Dax account with credits or an OpenRouter key. Uploads require a
  Dax account and are limited to 64 MB. Live account-backed AI/upload smoke tests
  are not included in the automated test suite.
- No automatic updates yet. Download and install a newer package manually.
- ARM64 packages are not available in this first release.

## Privacy

Libraries and recent project paths stay on your computer. Credentials are stored
in GNOME Keyring or KDE Wallet, never in a plaintext Dax file. Dax does not poll
your clipboard or send automatic analytics.

Ask sends your conversation and chosen image only when you press Ask. Uploads send
your chosen file to Dax only when you press Upload. **Uploaded links are public to
anyone who has the link.** Coding agents manage their own connections and permissions.

## Feedback

[Report a problem](https://github.com/DaxOrg/public.linux.getdax.app/issues/new).
Include your distribution, desktop (GNOME/KDE/etc.), X11 or Wayland, Dax version,
and steps to reproduce. Remove prompts, tokens, and other private information from
logs before sharing them.
