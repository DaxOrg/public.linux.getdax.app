# First beta validation

Version: **0.1.0-beta.1**  
Application source commit: `cb9e33a193a92353de2800a07c7d943abf986a9e`

Built for x86_64 Linux with Rust 1.91.1 in a Debian 12 build environment. The
optimized release build passed eight tests:

- HTTP errors and single-send behavior (no duplicate paid calls or uploads).
- SSH argument validation.
- Atomic library persistence and refusal to overwrite project instruction files.
- Attachment size limits and regular-file checks.
- GTK workflow: prompt save/search/copy, real VTE command execution, split sessions,
  hide/reopen behavior, navigation, and keyboard launcher activation.
- X11 global shortcut dispatch.
- Desktop Secret Service save/read/replace/list/delete round trip.

The actual release packages were installed in a fresh Ubuntu 24.04 container with
an Xvfb desktop and private D-Bus session. Checks passed for runtime dependencies,
SHA-256 checksums, desktop entry validation, application startup, single-instance
routing to Settings and Accelerators, quitting, package removal with library
retention, and installing/uninstalling the tar archive as a non-root user.

This validates the containerized X11 path, not a full interactive GNOME or KDE
session. Wayland portals, live account-backed AI/uploads, real remote SSH servers,
and installed third-party coding agents still need broader user testing. No real
credentials, paid AI calls, or public test uploads were used for these checks.
