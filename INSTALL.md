# Installing Dax for Linux

Download assets from the [0.1.0-beta.1 release](https://github.com/DaxOrg/public.linux.getdax.app/releases/tag/v0.1.0-beta.1).
This release is for **x86_64 (amd64)** computers.

## Verify your download

Download `SHA256SUMS` alongside the package and run:

```sh
sha256sum --ignore-missing -c SHA256SUMS
```

Checksums detect damaged downloads; they are not a separate cryptographic signature.

## Debian 12 / Ubuntu 24.04 or later

```sh
sudo apt install ./dax_0.1.0~beta.1_amd64.deb
```

APT installs the declared GTK, VTE, and other native library dependencies. A normal
logged-in desktop session with D-Bus is required. For Secrets and saved AI keys,
use GNOME Keyring or a Secret Service-compatible KDE Wallet. For screenshots and
Wayland shortcuts, install your desktop's XDG portal backend.

## Portable archive

Install GTK4 (4.8+), libadwaita (1.2+), VTE GTK4 (0.70+), OpenSSL 3, D-Bus, and
OpenSSH, and Python 3 on your distribution. Then extract the archive and install it for your user:

```sh
tar -xzf dax-0.1.0-beta.1-linux-x86_64.tar.gz
cd dax-0.1.0-beta.1-linux-x86_64
./install.sh
```

The installer writes the executable to `~/.local/bin/dax` and the desktop entry and
icon to `~/.local/share`. It does not need sudo. If `~/.local/bin` is not on your
PATH, launch Dax from the application menu or run `~/.local/bin/dax`.

Do not mix a system `.deb` installation and a user-local installation; choose one
method. To upgrade, quit Dax and install the new package using the same method.

## Shortcuts and tray

Inside Dax, Ctrl+K opens Accelerators; Ctrl+Shift+C/V copies and pastes in terminals.
Enable the global launcher shortcut in Settings for each running session. On X11,
it is Ctrl+Alt+Space. On Wayland, the desktop may ask you to approve a shortcut.
If the portal is unavailable, add a desktop custom shortcut for `dax --launcher`.

GNOME may require an AppIndicator extension for the tray icon. You can always
reopen Dax through the application menu. Closing its window hides it; **Quit Dax**
ends the application after confirming that running sessions may be disconnected.

## Remove Dax

For the `.deb`:

```sh
sudo apt remove dax
```

For the tar installation, use the included `./uninstall.sh`. Libraries and desktop
keyring entries are retained. Disconnect AI accounts and delete any vault entries
from Dax before uninstalling if you want them removed too.

## Troubleshooting

- **Missing agent:** install the agent in your Linux environment and ensure it is on
  PATH. Dax does not install agents or bypass their permission prompts.
- **Keyring unavailable:** start/unlock your desktop's Secret Service. Dax will show
  an error instead of storing a credential in a file.
- **Screenshot unavailable:** install your desktop portal backend or attach an image
  file in Ask instead.
- **No window after closing:** run `dax` again. `dax --settings` opens Settings and
  `dax --launcher` opens Accelerators in the existing instance.
- **Updates:** check the public repository's Releases page; this beta has no automatic
  updater.
