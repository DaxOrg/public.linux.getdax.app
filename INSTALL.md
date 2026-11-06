# Install Dax for Linux

Download [0.2.0-beta.1](https://github.com/DaxOrg/public.linux.getdax.app/releases/tag/v0.2.0-beta.1).
This release supports **x86_64 / amd64** computers.

## Verify the download

Download `SHA256SUMS` alongside your package:

```sh
sha256sum --ignore-missing -c SHA256SUMS
```

## Debian 12 / Ubuntu 24.04 or later

```sh
sudo apt install ./dax_0.2.0-beta.1_amd64.deb
```

Open **Dax** from the application menu, or run `dax`. APT installs the declared
native dependencies. The system package installs Chromium's official sandbox
helper with the permissions it requires. The application does not add a
`--no-sandbox` flag.

Upgrading replaces the application while retaining libraries in
`~/.local/share/dax` and credentials in the desktop keyring. Quit the previous
version before installing the update.

## User-local tar installation

Install your distribution's GTK3, NSS, ALSA, GBM, OpenSSL 3, D-Bus, DejaVu fonts,
OpenSSH, and Python 3 packages. Then:

```sh
tar -xzf dax-0.2.0-beta.1-linux-x86_64.tar.gz
cd dax-0.2.0-beta.1-linux-x86_64
./install.sh
```

The installer writes the application to `~/.local/lib/dax`, a launcher to
`~/.local/bin/dax`, and the desktop entry/icon to `~/.local/share`.
It uses Chromium's user-namespace sandbox. Desktops that restrict unprivileged
user namespaces should use the `.deb` installation instead. Do not disable the
application sandbox to work around an installation problem.

Choose one installation method; avoid leaving a system and user-local version
on PATH at the same time.

## First use

- Choose a folder in Shepherd, then add a shell or an already-installed agent.
- Ctrl+Alt+Space opens Accelerators inside Dax. Settings can enable it globally.
- Ctrl+Shift+K opens the project picker; Ctrl+Shift+J jumps to an agent.
- Ctrl+Shift+N adds an agent, Ctrl+Shift+T creates a tab, Ctrl+Shift+B folds the
  sidebar, and Ctrl+Shift+M zooms the selected pane.
- Closing the window hides Dax and preserves running sessions. Quit Dax from its
  tray menu or Settings → About to end them, with confirmation.
- For credentials, start/unlock GNOME Keyring or a Secret Service-compatible
  KDE Wallet. Dax never falls back to storing secrets in a JSON file.
- For screenshots and Wayland shortcuts, install your desktop's XDG portal
  backend. If global shortcuts are unavailable, bind `dax --launcher` through
  the desktop's keyboard settings.

`dax --settings`, `dax --launcher`, `dax --background`, `dax --quit`, and
`dax --version` are available through the installed launcher.

## Remove

For the system package:

```sh
sudo apt remove dax
```

For the user-local installation, run the archive's `./uninstall.sh`.
Libraries and keyring records are retained. Disconnect accounts and delete vault
entries inside Dax before uninstalling if you want those removed too.

## Troubleshooting

Check that agents are on PATH and authenticated in your Linux environment.
For a missing screenshot portal, attach an image file instead. GNOME may need an
AppIndicator extension to display the tray, but Dax remains accessible through
its application launcher. Updates are installed manually from GitHub Releases.
