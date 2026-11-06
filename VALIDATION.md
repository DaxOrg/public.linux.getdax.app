# 0.2.0-beta.1 validation

Application source: `4c262590c65dee9ef7460d15a04138b19a09b7fd`.

The Linux presentation was rebuilt in Electron using the macOS source design
measurements and Dax's artwork. Reference macOS checkout:
`84a8196c31b31476f8a4cbacae38c2b1d8f57a3f`.

Verified geometry includes the 528 px launcher, three columns of 143 px tiles,
19 px palette insets, 20 px panel corners, 54 px pane headers, 16 px terminal text,
856×600 snippet panel with a 336 px list, 580×600 Ask panel, and the separate
960×900 Settings window with its icon toolbar.

**19 automated tests passed:** five Rust core tests, two native platform tests,
one real Rust-service/PTY integration test, ten renderer interaction tests, and
one packaged Electron end-to-end test. The latter covers real terminal typing
and paste, split panes, visible terminal-column bounds, clipboard, local library
persistence, a global shortcut, a separate preferences window, shared appearance,
focus restoration, and the renderer/IPC boundary.

The renderer tests use explicit fixtures; they do not represent live AI calls.
The screenshots in this repository come from the actual Linux Electron app and
its real Rust service in an isolated test environment.

The system package and user-local installer passed checks in a disposable
Ubuntu 24.04 environment: dependencies, checksums, desktop entry, ordinary-user
file access, Chromium sandbox-helper permissions, removal, library retention,
and replacement of the old beta icon. The final package was also extracted and
checked for non-root executable/read access.

Docker GUI tests explicitly use Chromium's `--no-sandbox` switch because Docker
restricts namespace creation. Production launchers do not add that switch;
renderers use sandboxing, context isolation, and disabled Node integration.

Native file dialogs, desktop-compositor blur, and font rasterization can vary
across operating systems. Broad interactive GNOME/KDE/Wayland coverage, live
account-backed AI/uploads, and real remote-server testing remain outside this
validation. This is a visual-design update, not full macOS feature parity.
