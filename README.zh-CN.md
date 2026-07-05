# HOI4 Mod Utilities 中文说明

[English](README.md)

这是原项目 [hoi4modutilities](https://github.com/herbix/hoi4modutilities/) 的 mirror 和维护分支。项目目标不是重写插件，而是在原作者停止维护后，继续让这个轻量级 HOI4 mod 开发辅助工具适配当前游戏版本。

## 项目立场

原作者在 README 中写道：

> I'm disappointed by Paradox because of the Silk Road thing. I'll pause this project until they fix it.

这里的 "Silk Road thing" 指的是 Paradox 在 HOI4 内容中对丝绸之路相关叙事的处理问题。相关国策曾以 "Expand the Silk Road" 命名，并把帖木儿帝国势力范围、向中亚和周边地区扩张、从乌鲁木齐到赫拉特修建铁路等内容包装为“扩展丝绸之路”。后续只是将名称调整为更偏向帖木儿叙事的路线，并没有充分回应其历史语境问题。

这个 mirror 分支延续原作者对此问题的保留态度。丝绸之路是横跨欧亚大陆、由多条贸易和文化交流路线构成的复杂历史网络，不应被简化为服务某个不相干地区叙事的便利标签。HOI4 可以做架空和玩法设计，但涉及真实历史概念时，仍应尊重基本史实、资料来源和历史语境。

本项目的维护工作聚焦在工具本身：让国策树、科技树、地图、事件、GUI、GFX 和贴图预览继续适用于当前版本游戏和常见 mod 开发流程。

## 功能

* 世界地图预览
* 国策树预览
* 事件树预览
* 科技树预览
* 军工组织（MIO）预览
* GUI 预览
* `.gfx` 精灵预览
* `.dds`、`.tga` 图片预览

## 使用方式

1. 在 VS Code 中安装并启用扩展。
2. 设置 Hearts of Iron IV 安装目录，也就是 `hoi4ModUtilities.installPath`。
3. 打开你的 mod 开发目录。
4. 可选：使用 `Select mod file` 选择当前工作的 `.mod` 文件。
5. 在国策、科技、事件、地图、GUI 或 `.gfx` 等文件中使用 `Preview HOI4 file` 预览。

## 当前维护重点

* 适配新版 HOI4 和 DLC 新增字段。
* 改善国策树预览，尤其是动态 icon、overlay、mod 自定义 GFX 资源加载。
* 改善科技树预览，尤其是新版小布局科技、图标 fallback 和整体缩放截图体验。
* 保持插件轻量，不把内部兼容性扫描做成用户无关的新功能。

## 演示

### 世界地图预览

![World map preview demo](demo/5.gif)

### 国策树预览

![Focus tree preview demo](demo/1.gif)

### 事件树预览

![Event tree preview demo](demo/6.gif)

### 科技树预览

![Technology tree preview demo](demo/4.gif)

### GUI 预览

![GUI preview demo](demo/7.gif)

## 扩展设置

| 设置 | 类型 | 说明 |
| --- | --- | --- |
| `hoi4ModUtilities.installPath` | `string` | Hearts of Iron IV 安装目录。未设置时，大多数功能无法正常工作。 |
| `hoi4ModUtilities.loadDlcContents` | `boolean` | 预览文件时是否加载 DLC 图片。启用后会占用更多内存。 |
| `hoi4ModUtilities.modFile` | `string` | 当前工作的 `.mod` 文件路径，用于读取 `replace_path`。未指定时，会使用第一个工作区文件夹中的第一个 `.mod` 文件。 |
| `hoi4ModUtilities.enableSupplyArea` | `boolean` | 如果你正在开发 HOI4 1.10 或更早版本的 mod，可用它检查 supply area。 |
| `hoi4ModUtilities.previewLocalisation` | `enum` | 事件树预览使用的本地化语言。 |
| `hoi4ModUtilities.featureFlags` | `array` of `string` | 功能标记，用于启用或禁用部分功能。修改后需要重新加载窗口。详情见原项目 Wiki。 |

## 已知问题

* 国策树 GUI 不能像科技树一样完全通过游戏 GUI 文件配置。
* 世界地图边缘线有时不能完全贴合颜色边界。
* 如果同一事件来自不同选项，事件树预览可能重复显示该事件。

## Release Notes - [0.12.2]

### Fixed

* 允许 symbol 类型中出现 `|`，以支持 `localization_key = building_state_modifier|dam` 这类写法（#105，贡献者：[IShiraiKurokoI(Shirai_Kuroko)](https://github.com/IShiraiKurokoI)）。

## 贡献

* 如果你有建议，可以在本 mirror 仓库提交 issue。
* 如果你想贡献翻译，可以提交 pull request。本地化相关文件位于 `i18n` 目录。
* 感谢原项目的所有贡献者。
