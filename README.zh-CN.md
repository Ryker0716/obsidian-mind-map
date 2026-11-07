[English](README.md) | 简体中文

# Obsidian Mind Map — 社区维护版（中文说明）

![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/Ryker0716/obsidian-mind-map?sort=semver)

本仓库是 [James Lynch 开发的 Obsidian Mind Map](https://github.com/lynchjames/obsidian-mind-map) 的社区维护分支，沿用原项目的 MIT 许可证。

原插件自 2020 年起不再更新，已无法在当前版本的 Obsidian 上启动。本分支持续跟进兼容性修复并维护安装说明；功能层面的改进会在时间允许时进行。

本插件基于 [Markmap](https://markmap.js.org/)，把 [Obsidian](https://obsidian.md/) 的 Markdown 笔记渲染成思维导图。

### 本分支的改动（v1.1.1）

- 修复在当前 Obsidian 版本上无法启动的问题（已在 Obsidian 1.15.0 实测通过）。
- 修复围栏代码块导致整篇导图无法渲染的问题。因为 Prism 的运行时 CommonJS 语言加载器在插件打包产物中不可用，代码块会以纯文本显示；KaTeX 公式渲染保持可用。
- 保持预览视图与原 Markdown 笔记的关联，并在首次打开时立即完成渲染。
- 修复当前 Rollup 工具链下的 TypeScript 处理。

问题反馈：[Ryker0716/obsidian-mind-map/issues](https://github.com/Ryker0716/obsidian-mind-map/issues)

### 原项目相关链接

[Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=gera2ld.markmap-vscode) 上也有 Markmap 官方出品的类似插件。

## 功能

- 把当前笔记预览为思维导图
- 切换其他面板时，思维导图预览会随之更新，交互方式类似 [Local Graph](https://forum.obsidian.md/t/how-to-open-a-local-graph-view-pane-on-the-right-sidebar/7190)、[Outline](https://publish.obsidian.md/help/Plugins/Outline) 和 [Backlink](https://publish.obsidian.md/help/Plugins/Backlinks) 面板

![Mind Map Demo Image](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-demo.png)

## 用法

通过命令面板执行对应命令，即可把当前笔记打开为思维导图预览。

![Mind Map Preview Command](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-preview-command.png)

### 预览视图的更多选项

思维导图预览视图的「更多选项」菜单里有两个功能：

![Mind Map Preview More Options](https://raw.githubusercontent.com/lynchjames/obsidian-mind-map/main/images/mind-map-view-more-options.png)

#### 钉住（Pin）

把思维导图预览面板钉在当前笔记上，这样切换到其他笔记时导图仍保持原位。面板标题栏会出现一个图钉图标，点击即可取消钉住。

#### 复制截图（Copy screenshot）

把思维导图 SVG 复制到剪贴板，可以直接粘贴到 Obsidian 笔记或图片编辑器里。

## 兼容性

本分支的发行版保留原插件 ID（`obsidian-mind-map`）。v1.1.1 已在 Obsidian 1.15.0 上测试。

## 安装本分支

本分支不在官方社区插件市场分发。可通过 [BRAT](https://github.com/TfTHacker/obsidian42-brat) 或手动方式安装 GitHub Release。

### BRAT

在 Obsidian 中执行 **BRAT: Add a beta plugin for testing**，输入 `Ryker0716/obsidian-mind-map`，然后启用已安装的插件。如果与已装的社区版冲突，先备份其 `data.json`，通过 BRAT 重装后再恢复该设置文件。

### 手动安装

1. 从[本分支最新 Release](https://github.com/Ryker0716/obsidian-mind-map/releases/latest) 下载 `main.js` 和 `manifest.json`。
2. 把这两个文件放进 `<vault>/.obsidian/plugins/obsidian-mind-map/`。
3. 确认该目录里已有你的设置文件 `data.json`（如有需要，先从原插件目录备份并复制过来）。
4. 重启 Obsidian，并在社区插件里启用 **Mind Map**。

从原版升级时，只需替换 `main.js` 和 `manifest.json`，保留 `data.json`。本分支保留原插件 ID，可以原位无缝升级；如果 BRAT 提示插件已存在，先移除旧的 BRAT beta 条目，再重新添加本仓库。

### 构建与验证

```sh
npm install
npm run build
node --check dist/main.js
```

发布工作流会构建 `dist/main.js`；构建产物不入库。原项目的测试命令依赖旧版 Mocha/yargs 工具链，仓库本身也没有测试目录；兼容性验证以在 Obsidian 中加载产物并打开含围栏代码块的笔记为准。

## 贡献

欢迎针对兼容性修复提交聚焦的 PR 到本分支的 Issue / PR 列表。原插件采用 MIT 许可证，版权归 James Lynch 所有。

## 致敬原作者

本插件的一切起点，都是 James Lynch 在 2020 年开发的 [obsidian-mind-map](https://github.com/lynchjames/obsidian-mind-map)。感谢他为 Obsidian 社区带来这款优雅易用的 Markmap 插件，也感谢他选择以 MIT 许可证开源，让后来的维护者能够站在他的肩膀上继续前行。

本分支的所有维护工作，都以延续原项目为出发点；没有原作，就没有这个 fork。如果你觉得这个插件好用，欢迎支持原作者：[PayPal](https://paypal.me/lynchjames2020)（该捐赠链接属于 James Lynch 本人，与本分支维护者无关）。
