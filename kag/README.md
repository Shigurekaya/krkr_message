# KAG 脚本层 — 开发者文档

> 本目录为 **中文开发者文档** 入口。  
> 引擎子模块 `engine/script/` 内日文 README 的说明已翻译并整理于此；**请勿直接修改子模块** 来做汉化或项目定制。
>
> **最新维护版**在 **[krkr_message](https://github.com/Shigurekaya/krkr_message)** 仓库的 `kag/` 目录。  
> gal- 内本目录可能与 krkr_message 不同步；以 krkr_message 为准。  
> 三库说明见 [docs/GITHUB-AI-GUIDE.md](../docs/GITHUB-AI-GUIDE.md)。

---

## 文档索引

| 文档 | 内容 |
|------|------|
| [KAG3-说明.md](KAG3-说明.md) | 标准 KAG3 for krkrz 是什么、与 `_template` 的关系 |
| [KAG3_Ham-说明.md](KAG3_Ham-说明.md) | Ham 扩展（图形存读档 / 设置 / 功能菜单） |
| [KAG-标签参考.md](KAG-标签参考.md) | 写 `.ks` 剧本时的标签速查 |
| [Config-常用项.md](Config-常用项.md) | `Config.tjs` 常用配置索引 |
| [引擎选项说明.md](引擎选项说明.md) | krkrz `--userconf` 与 `option_desc_ja.json` |
| [编译说明.md](编译说明.md) | 从源码编译 krkrz（扩展索引；原位文档见 `engine/HowToBulid.md`） |
| [发行与XP3.md](发行与XP3.md) | Releaser、XP3 封包与 GPL 发行（原位见 `engine/document/misc_markdown/tools/releaser.md`） |
| [docs/汉化范围.md](../docs/汉化范围.md) | 指针 → [krkr_message 权威版](https://github.com/Shigurekaya/krkr_message/blob/main/docs/汉化范围.md) |

---

## 源码位置（子模块，参考用）

| 路径 | 说明 |
|------|------|
| `engine/script/KAG3/` | KAG3 官方脚本（UTF-8；`data/` 占位说明已中文化） |
| `engine/script/KAG3_Ham/` | 内置 Ham 扩展的 KAG3（图形系统 UI，未默认启用） |
| `engine/script/Sample/` | 官方示例与工具 |
| `engine/document/kirikiriz/` | 官方 HTML 参考（入口页/目录已中文化；API 正文页仍为日文，在线版见下） |

**实际运行** 使用 `projects/<作品>/data/`，由 `ops/run-project.ps1` 联接到 `runtime/win32/data/`。

---

## 本仓库运行版（已汉化）

| 路径 | 说明 |
|------|------|
| `projects/_template/data/system/` | 从 KAG3 复制并汉化的 21 个 system 脚本 |
| `projects/_template/data/scenario/` | 示例剧本 `.ks` |
| `projects/_template/data/others/readme.txt` | 玩家向中文操作说明 |

新建项目：

```powershell
.\ops\init-project.ps1 -Name 我的作品
```

---

## 常用 KAG 标签（摘要）

| 标签 | 用途 |
|------|------|
| `@talk` / `@narr` 或纯文本行 | 对话 / 旁白 |
| `[image layer=base]` + `[trans]` | 切换背景 |
| `[image layer=N]` | 立绘层 |
| `[playbgm]` / `[playse]` | BGM / 音效 |
| `@sel` / `[jump]` | 选项 / 跳转 |
| `[save]` / `[load]` | 存读档 |
| `[cm]` / `[r]` / `[l]` / `[s]` | 清屏 / 换行 / 等待 |

完整列表见 [KAG-标签参考.md](KAG-标签参考.md)。

---

## 官方在线文档（原文日文）

完整 KAG3 / TJS 规范以官网为准（英文站名、日文正文）：

- [KAG3 文档索引](https://krkrz.github.io/krkr2doc/kag3doc/contents/index.html)
- [KAG3 键鼠操作](https://krkrz.github.io/krkr2doc/kag3doc/contents/MouseKeyboard.html)
- [吉里吉里 Z 参考](https://krkrz.github.io/docs/kirikiriz/j/contents/index.html)
- [TJS2 参考](https://krkrz.github.io/docs/tjs2/j/contents/index.html)

---

## 相关仓库文档

| 文档 | 用途 |
|------|------|
| [项目说明.md](../项目说明.md) | 分层架构、启动、插件 |
| [runtime/README.md](../runtime/README.md) | 运行时说明（`runtime/win32/readme.txt`） |
| [Config-常用项.md](Config-常用项.md) | 键位、分辨率、存档等 Config 索引 |
| [运维指南.md](../docs/运维指南.md) | 环境、打包、排错 |
| [projects/README.md](../projects/README.md) | 项目目录说明 |
