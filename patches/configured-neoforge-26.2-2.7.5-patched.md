# Configured 2.7.5 (NeoForge 26.2), patched

This pack re-hosts `configured-neoforge-26.2-2.7.5-patched.jar` on its "external" release. It is MrCrayfish's
Configured, licensed under the GNU LGPL 3.0, with one compatibility fix so it loads on NeoForge 26.2.0.86.

- Upstream source and licence: https://github.com/MrCrayfish/Configured (LGPL-3.0)
- Built from: the official Configured 2.7.5 NeoForge jar for 26.2.

## What was changed

One call, in the client events class (`NeoForgeClientEvents`): Configured opened NeoForge's mod list screen with

    new ModListScreen(screen)

and NeoForge 26.2 moved that screen and replaced its constructor with a factory, so the call is now

    ModListScreen.create(screen)        // NeoForge's gui.modlist.ModListScreen (was gui.ModListScreen)

The change was made to the compiled class. The jar's signature was removed, as a signed jar won't load with a changed
class. Nothing else in the jar differs from the official release.

When an official Configured build for 26.2 exists, the pack goes back to it and this file and the re-hosted jar go.
