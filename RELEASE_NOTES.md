# Dax for Linux 0.2.0-beta.1

This update replaces the first beta's GTK presentation with the macOS Dax visual
design, rendered in HTML/CSS through Electron with the existing Rust services.

- Project sidebar, collapsible navigation, tab lane, colored pane headers, and
  16-pixel terminal text.
- The 528-pixel, three-column launcher with macOS tile measurements, icon wells,
  selection glow, keyboard navigation, arrangement, pinning, and sorting.
- The 856×600 Prompt Snippets panel with a 336-pixel list, preview stage,
  My Snippets / Snippet Library tabs, and copy/type modes.
- The 580×600 shared Ask / Image Ask panel, compact composer, Markdown answers,
  image previews, and pending answers preserved across panel close/reopen.
- A separate macOS-style Settings window with an icon toolbar, plus dark/light
  appearance, Dax accent choices, and the original app/agent artwork.
- Real PTYs and the existing libraries, keyring credentials, AI and upload clients.

Download `dax_0.2.0-beta.1_amd64.deb` or
`dax-0.2.0-beta.1-linux-x86_64.tar.gz` with `SHA256SUMS`.

```sh
sha256sum --ignore-missing -c SHA256SUMS
sudo apt install ./dax_0.2.0-beta.1_amd64.deb
```

The system package is recommended for Debian 12 / Ubuntu 24.04. Existing Linux
libraries and desktop-keyring credentials are retained.

The application uses the same design measurements; native dialogs, compositor
blur, and font rasterization remain platform-dependent. Full macOS feature parity,
ARM64 packages, automatic updates, and broad Wayland/live-service validation are
still future work. No fake controls are shown for unported features.

[Installation](https://github.com/DaxOrg/public.linux.getdax.app/blob/main/INSTALL.md)
· [Feedback](https://github.com/DaxOrg/public.linux.getdax.app/issues/new)
