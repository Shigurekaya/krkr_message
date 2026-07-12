# 发行与 XP3 打包

> 原文：`engine/document/misc_markdown/tools/releaser.md`（已原位汉化）  
> 说明 krkrz **发行工具（Releaser）** 与 **XP3 封包** 的现状；Gal 作品最终发行时常用到。

---

## Releaser（发行器）

**吉里吉里 Z 目前不提供自带的 Releaser。**

请使用 **吉里吉里 2 发行包** 中附带的 Releaser 工具。  
下载：https://krkrz.github.io/download/kr2_232r2.zip（与 [runtime/win32/readme.txt](../runtime/win32/readme.txt) 中说明一致）

**将归档文件合并进 exe 本体** 的方式，在吉里吉里 Z 中 **尚不支持**（与 krkr2 不同）。

### 替换 exe 图标

不要用 krkr2 的 Releaser 改图标；请使用 **通用资源编辑器** 修改 exe 资源。  
可搜索「免费软件 图标 修改 exe」等关键词选择工具。

---

## 本仓库当前的发行方式

| 方式 | 脚本 / 路径 | 说明 |
|------|-------------|------|
| **散文件文件夹**（默认） | `ops/pack-release.ps1` | 输出 `dist/<项目名>/`：`krkrz.exe` + `plugin/` + `data/` + `license.txt` |
| **XP3 封包**（进阶） | krkr2 官方 **krkrrel** 等 | 需手动操作；见 [运维指南](../docs/运维指南.md) § XP3 |

散文件方式适合开发迭代与 GPL 合规；商业 Gal 常见 **多个 `.xp3` 分包**（`scenario.xp3`、`bgimage.xp3` 等），本仓库 **尚未** 提供 XP3 一键脚本。

---

## XP3 与 KAG 项目结构

KAG 运行时通过 `Initialize.tjs` 中的 `useArchiveIfExists` 按顺序加载：

```tjs
useArchiveIfExists("scenario.xp3");
useArchiveIfExists("bgimage.xp3");
// …
useArchiveIfExists("patch.xp3");  // 汉化/更新补丁常放在最后
```

开发阶段本仓库用 **目录联接** 直接读 `projects/<名>/data/`，无需 XP3。  
发行前再用 krkrrel 将 `data/` 下各目录分别封包，或与 exe 同目录放置散文件。

---

## GPL 分发注意

krkrz 为 **GPL** 授权。分发含 `krkrz.exe` 的成品时：

- 附带 `license.txt`
- 提供源码获取方式说明（见 `pack-release.ps1` 输出结构）

---

## 延伸阅读

- [编译说明.md](编译说明.md)
- [运维指南 — XP3 封包](../docs/运维指南.md)
- [项目说明 — 发行](../项目说明.md)
