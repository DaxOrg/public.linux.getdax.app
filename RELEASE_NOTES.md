# Dax for Linux 0.1.0-beta.1

The first public Linux beta is ready to try on x86_64 desktops.

## Included

- Shepherd with embedded agent terminals, tabs, two-pane sessions, recent projects,
  and SSH using your existing OpenSSH setup.
- Prompt Snippets, Frequent CLIs, Inject MD, and desktop-keyring-backed Secrets.
- Ask AI / Image Ask with conversation history, image attachments, and optional
  portal screenshots. Connect a Dax invite code or your OpenRouter key in Settings.
- Image to URL and File Drop with explicit upload and public-link copy.
- Searchable launcher, tray, desktop entry, single-instance activation, and
  optional global launcher shortcut.

## Install

Download `dax_0.1.0-beta.1_amd64.deb` and `SHA256SUMS`:

```sh
sha256sum --ignore-missing -c SHA256SUMS
sudo apt install ./dax_0.1.0-beta.1_amd64.deb
```

Or download `dax-0.1.0-beta.1-linux-x86_64.tar.gz` and follow the included
`INSTALL.md`. Debian 12 and Ubuntu 24.04 are the initial package targets.

Open Dax, choose a project, and start a shell or an agent you already have installed.
No account is needed for local features. AI requires valid credentials and credits;
file uploads require a Dax account and create public links.

## Validation and limits

The Linux build is exercised with automated local-storage, HTTP, command-validation,
X11 shortcut, desktop-keyring, and GTK/VTE workflow tests. These verify prompt
save/search/copy, terminal command execution, split sessions, and hide/reopen behavior.

This is an early beta, not full macOS parity. Interactive GNOME/KDE/Wayland coverage
is still needed. Portal screenshots and shortcuts depend on your desktop backend;
`dax --launcher` can be assigned as a custom desktop shortcut. Live account-backed
AI and uploads are not exercised by the automated tests.

No ARM64 binary, automatic updater, restored terminal processes, multiplayer,
custom cloud storage, image generation, background removal, or screen markup yet.

[Installation and troubleshooting](https://github.com/DaxOrg/public.linux.getdax.app/blob/main/INSTALL.md)
· [Report an issue](https://github.com/DaxOrg/public.linux.getdax.app/issues/new)
