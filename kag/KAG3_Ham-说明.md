# 鱧入り KAG3 for 吉里吉里 Z — 说明

> 原文：`engine/script/KAG3_Ham/README.md`（已原位汉化）  
> 「鱧入り」= 内置 **Ham 扩展** 的 KAG3；Ham 扩展源自日本社区工具 **鱧天（Hamoten）** for 吉里吉里 2。

---

## 是什么

本项目从 **KAG3 for 吉里吉里 Z** 分叉，在标准 KAG3 之上增加 **Ham 扩展**，提供：

| 功能 | 说明 |
|------|------|
| 图形化存档 / 读档界面 | 槽位、缩略图、日期、备注 |
| 图形化设置（Config）界面 | 音量、文字速度、自动播放间隔等 |
| 带滚动条的对话履历 | 比纯 KAG3 履历 UI 更完整 |
| 功能菜单 | 右键或屏幕角落按钮呼出 |
| 快速存档（Quick Save） | 可配置槽位与按钮位置 |

设计目标：在 **尽量不损失 KAG3 可定制性** 的前提下，让初次使用吉里吉里 Z / KAG3 的作者也能做出外观尚可的系统界面。

Ham 扩展的代码与 UI 资源位于 `data/system/Ham/`（脚本 + `assets/` 图片）。

## 与鱧天（Hamoten）的差异

| 项目 | 鱧入り KAG3 | 鱧天 for krkr2 |
|------|-------------|----------------|
| 分辨率 | 可在一定程度上自由更改（建议 ≥800×600；HD 需换 UI 素材） | 相对固定 |
| 剧本文件路径 | 无特殊限制 | 有约定 |
| 场景跳过 | **未实现** | 有 |
| 立绘格式 | 无特殊限制；**目パチ（眨眼）未实现** | 有配套方案 |
| 事件 CG 路径 | 无特殊限制；**CG 鉴赏模式未实现** | 有 |
| 「随处存档」插件 | **未同捆** | 有 |
| 鱧天自带宏 | 除少数外 **未定义** | 大量内置 |
| 易用性 vs 自由度 | 自由度更高，开箱即用程度略低 | 更省事 |

鱧天 for 吉里吉里 Z 当时仍在准备中；将鱧天 for krkr2 的脚本改为 UTF-8，并把 system 换为 KAG3 for 吉里吉里 Z，即可在 krkrz 上近似运行。

## 发行建议

吉里吉里 Z **不推荐依赖菜单栏**；使用鱧入り KAG3 发行时，建议 **关闭菜单栏**，改由 Ham 功能菜单提供系统操作。

菜单栏约八成能力可由 Ham 功能菜单覆盖。当前 **尚未** 从功能菜单直接调用的包括：字体更改、回退（Rollback）、「关于本软件」等（「关于」可自行用 TJS 扩展）。

## 启用方式

在项目的 `data/system/Config.tjs` 中：

```tjs
;global.useHamExtention = true;
```

并将 `engine/script/KAG3_Ham/data/system/`（含 `Ham/`）复制到项目的 `data/system/`，或在新建项目时选用 Ham 版 system。

**本仓库默认模板 `_template` 使用纯 KAG3（已汉化），未启用 Ham。**

## UI 资源位置

```
data/system/Ham/
├── Ham.tjs              # 扩展入口
├── Preferences.tjs      # Ham 布局与颜色配置
├── MenuSettings.tjs     # 右键功能菜单项
└── assets/
    ├── bookmark/        # 存读档界面
    ├── userconf/        # 设置界面
    └── history/         # 履历界面
```

默认 UI 为白底网格 + 英文标题图（SAVE / LOAD / CONFIG）+ 部分日文菜单文案；汉化需同时改 **脚本字符串** 与 **assets 图片**。

## 许可

KAG3 License  
Copyright (C)2001-2009, W.Dee and contributors — 可自由修改与再分发。

---

## 延伸阅读

- [KAG 脚本层总览](README.md)
- [KAG3 说明](KAG3-说明.md)
- [KAG3 说明](KAG3-说明.md) — 标准 KAG3 与 Ham 扩展的取舍
