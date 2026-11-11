# Explorer

A file tree beside the chat, like the Explorer in VS Code. It shows the folder you're working in so you can watch what Claude and each CXL plugin create, file by file.

## What it shows

- **Your folders and files.** Click a folder to open or close it. Click a file to open it in the Files pane. HTML files also get **↗ browser** to open them in the Browser pane.
- **Git status letters**, as VS Code marks them: **U** new, **A** added, **M** modified, **R** renamed, **↑** committed but not pushed. A folder holding unsaved changes is coloured and carries a dot.
- **Live highlight.** The file Claude is writing right now is highlighted, and "Just changed by Claude" lists what it wrote this session.
- **The plugin map.** A thin coloured line on each row shows which CXL plugin set up that folder (personal-os, marketing-brain, campaign-engine, reporting-agent, visual-brain, product-visual) or created that file. The key under the header lists the plugins on screen; open `raw/`, `wiki/` or `projects/` to see the module folders. What plugins created is kept in `.claude/plugin-map.json`.

It reads your own folder names from `.claude/folders.json`, so a rerouted personal OS maps correctly.

## Commands

- `/explorer` opens the pane. `/explorer plain` opens a simpler text view.
- `/plugin-map` switches the plugin colours on or off.

## Turning it off

Explorer follows the `/mods` switchboard if you have one installed. Off there writes `"explorer": false` to `~/.claude/mods/switches.json`, and Explorer then closes its pane, stops tracking edits and keeps `/explorer` from opening it, in every chat, within a few seconds. On again: run `/explorer`.

## Install

In the desktop app's **Code** tab or a terminal session:

```
/plugin marketplace add conversionxl/cxl-explorer-mod
/plugin install explorer@cxl-explorer-mod
```

The pane draws in the desktop app and the terminal. It does not run in Cowork or chat.

Explorer is also listed in the [`cxl-plugin`](https://github.com/conversionxl/cxl-plugin) marketplace, which reads it from this repo. Install it from one marketplace only, or `/explorer` loads twice.

### Moving from cxl-personal-os-plugins

Explorer used to ship in `cxl-personal-os-plugins` as `explorer@cxl-personal-os-plugins`. It was taken out of that marketplace on 10 November 2026 and lives here now. If you installed it from there, remove the old copy and add it from here:

```
/plugin uninstall explorer@cxl-personal-os-plugins
/plugin marketplace add conversionxl/cxl-explorer-mod
/plugin install explorer@cxl-explorer-mod
```

## Changing it

Change it in this repo by pull request, and bump `version` in `.claude-plugin/plugin.json` so installed copies pick it up with "Check for updates".
