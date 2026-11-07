English | [简体中文](README.zh-CN.md)

# Obsidian Mind Map — Community Maintenance Fork

![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/Ryker0716/obsidian-mind-map?sort=semver)

A maintained fork of [James Lynch's Obsidian Mind Map](https://github.com/lynchjames/obsidian-mind-map), distributed under the original MIT license.

The upstream plugin has not been updated since 2020 and cannot start on current Obsidian releases. This fork tracks compatibility fixes and installation instructions for this distribution; feature improvements are handled when time permits.

This plugin displays [Obsidian](https://obsidian.md/) Markdown notes as mind maps using [Markmap](https://markmap.js.org/).

### Changes in this fork (v1.1.1)

- Starts correctly on current Obsidian releases (verified on Obsidian 1.15.0).
- Prevents fenced code blocks from breaking the whole mind-map render. Code blocks display as plain text because Prism's runtime CommonJS language loader is unavailable in the plugin bundle; KaTeX remains enabled.
- Keeps the preview associated with the Markdown source note and renders immediately on first open.
- Fixes TypeScript processing with the current Rollup toolchain.

Issues: [Ryker0716/obsidian-mind-map/issues](https://github.com/Ryker0716/obsidian-mind-map/issues)

### Original project links

A similar plugin is available for [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=gera2ld.markmap-vscode).
    
## Features

- Preview your current note as a Mind Map
- Mind Map preview updates as you select other panes, similar to the [Local Graph](https://forum.obsidian.md/t/how-to-open-a-local-graph-view-pane-on-the-right-sidebar/7190), [Outline](https://publish.obsidian.md/help/Plugins/Outline) and [Backlink](https://publish.obsidian.md/help/Plugins/Backlinks) panes

![Mind Map Demo Image](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-demo.png)

## Usage

You can open the Mind Map preview for the current note with a command.

![Mind Map Preview Command](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-preview-command.png)


### Preview More Options Menu

The Mind Map Preview view has 2 options from the "more options" menu:

![Mind Map Preview More Options](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-view-more-options.png)

#### Pin

Allows you to pin the Mind Map preview pane to the current note so that you can select other notes with the current Mind Map remaining in place. A pin icon will appear in the header of the Mind Map preview pane. Click the pin icon to unpin.

#### Copy screenshot

Places a copy of the Mind Map SVG on your clipboard allowing you to paste it into a note in Obsidian or into an image editor of your choice.

## Compatibility

Community releases preserve the original plugin ID (`obsidian-mind-map`). Version 1.1.1 was tested on Obsidian 1.15.0.

## Installing this fork

This fork is not the official community-plugin distribution. Install the GitHub release with [BRAT](https://github.com/TfTHacker/obsidian42-brat) or manually.

### BRAT

In Obsidian, run **BRAT: Add a beta plugin for testing**, enter `Ryker0716/obsidian-mind-map`, and enable the installed plugin. If an existing community copy conflicts, back up its `data.json`, reinstall through BRAT, and restore the settings file.

### Manual installation

1. Download `main.js` and `manifest.json` from the [latest fork release](https://github.com/Ryker0716/obsidian-mind-map/releases/latest).
2. Put both files in `<vault>/.obsidian/plugins/obsidian-mind-map/`.
3. Ensure the folder already contains your settings as `data.json` (copy it from the previous plugin folder after backing it up if needed).
4. Reload Obsidian and enable **Mind Map** in Community plugins.

Upgrade from upstream by replacing only `main.js` and `manifest.json`, keeping `data.json`. This fork preserves the original plugin ID for seamless in-place upgrades; if BRAT reports that the plugin already exists, remove its stale BRAT beta entry and add this repository instead.

### Build and verify

```sh
npm install
npm run build
node --check dist/main.js
```

The release workflow builds `dist/main.js`; generated artifacts are not committed. The upstream test command uses a legacy Mocha/yargs toolchain and the repository has no test directory; compatibility verification should include loading the bundle in Obsidian and opening a note with fenced code blocks.

## Original project development

The original plugin is MIT licensed, copyright James Lynch. Contributions of focused compatibility fixes are welcome on the fork issue tracker.

## Donating to the original author

This fork exists thanks to James Lynch's original work. The original donation links belong to James Lynch, not to this fork:

Original donation: [PayPal](https://paypal.me/lynchjames2020). 中文说明与致谢见 [README.zh-CN.md](README.zh-CN.md)。
