# KAG3 for 吉里吉里 Z — 说明

> 原文：`engine/script/KAG3/README.md`（已原位汉化）  
> 本页为开发者文档的中文说明；上游 LICENSE 仍以子模块内文件为准。

---

本目录（`engine/script/KAG3/`）下的数据与脚本，是在 **KAG3** 基础上为 **吉里吉里 Z（krkrz）** 做最低限度适配后的版本。

- 随 beta 版附带的资源已转换为 **UTF-8** 编码。
- **菜单栏在全屏模式下不受支持**，全屏时菜单可能无法按预期工作（krkrz 官方限制）。

## 与本仓库的关系

| 位置 | 用途 |
|------|------|
| `engine/script/KAG3/` | 官方日文 KAG3 参考源码（Git 子模块，勿直接改） |
| `projects/_template/data/system/` | 从 KAG3 复制并已 **汉化** 的运行版 system 脚本 |
| 实际运行 | 通过 `ops/run-project.ps1` 联接 `projects/<名>/data/` 到 `runtime/win32/data/` |

新建项目请使用 `_template`，不要直接把 `engine/script/KAG3/data/` 当作运行目录。

## 许可

KAG3 License  
Copyright (C)2001-2009, W.Dee and contributors — 可自由修改与再分发。

---

## 延伸阅读

- [KAG 脚本层总览](README.md)
- [KAG 标签参考](KAG-标签参考.md)
- [Config.tjs 常用项](Config-常用项.md)
- [KAG3 在线文档（原文日文）](https://krkrz.github.io/krkr2doc/kag3doc/contents/index.html)
