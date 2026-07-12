# KAG 标签参考（开发者速查）

> 面向本仓库 `projects/*/data/scenario/*.ks` 写作。  
> 完整、权威说明见 [KAG3 在线文档（原文日文）](https://krkrz.github.io/krkr2doc/kag3doc/contents/index.html)。

语法要点：

- 标签以 `[` 开头、`]` 结束；行首 `@` 为宏/子程序。
- 属性用 `名=值`；字符串可加引号。
- `[cm]` 清屏；`[r]` 换行；`[l]` / `[p]` 等待点击；`[s]` 等待后停止。

---

## 1. 流程与跳转

| 标签 / 写法 | 用途 | 示例 |
|-------------|------|------|
| `*标签名\|显示名` | 定义跳转锚点 | `*start\|开始` |
| `[jump target=标签名]` | 跳转到标签 | `[jump target=start]` |
| `[call target=标签名]` | 调用子程序后返回 | |
| `[return]` | 从子程序返回 | |
| `[wait time=毫秒]` | 等待 | `[wait time=300]` |
| `[stop]` / `[s]` | 停止等待输入 | `[s]` |

---

## 2. 文本与对话

| 标签 | 用途 | 说明 |
|------|------|------|
| 纯文本行 | 旁白 / 对话 | 写在标签外，由 MessageLayer 显示 |
| `[cm]` | 清除消息层 | 新段落前常用 |
| `[r]` | 换行 | |
| `[l]` | 行末等待（点击继续） | |
| `[p]` | 页末等待（清页） | |
| `[deffont ...]` | 默认字体 | `face` `size` `color` 等 |
| `[emb exp="表达式"]` | 嵌入 TJS 表达式 | 如 `[emb exp="System.title"]` |
| `@talk` / `@narr` | 宏式对话（若项目定义） | 模板示例以纯文本为主 |

---

## 3. 图像与演出

| 标签 | 用途 | 示例 |
|------|------|------|
| `[image layer=base storage=文件]` | 背景（base 层） | `storage=room01` 或带路径 |
| `[image layer=N storage=...]` | 立绘 / 前景层 | `layer=1` 常见为角色层 |
| `[backlay]` / `[layopt]` | 层选项 | 透明度、定位等 |
| `[trans method=... time=...]` | 画面过渡 | 与 `[wt]` 连用 |
| `[wt]` | 等待过渡结束 | |
| `[freeimage layer=N]` | 释放层图像 | |
| `[position layer=message0 ...]` | 消息层位置/大小 | 见 `about.ks` |

素材路径约定（`Initialize.tjs` 已配置）：

| 目录 | 内容 |
|------|------|
| `bgimage/` | 背景 |
| `fgimage/` | 立绘 |
| `image/` | 其他图片 |
| `rule/` | 过渡规则图 |

---

## 4. 音频

| 标签 | 用途 | 示例 |
|------|------|------|
| `[playbgm storage=...]` | 播放 BGM | 文件通常在 `bgm/` |
| `[stopbgm]` | 停止 BGM | |
| `[playse storage=...]` | 播放音效 | 文件通常在 `sound/` |
| `[stopse]` | 停止音效 | |

---

## 5. 选项与分支

| 标签 | 用途 |
|------|------|
| `@sel` / 选项宏 | 分支选项（依项目 system 定义） |
| `[link target=...]` / `[click]` | 可点击链接文本（高级） |

模板最小示例仅含线性剧本；分支请参考 KAG3 官方 `@sel` 文档。

---

## 6. 存档

| 标签 | 用途 |
|------|------|
| `[save]` | 打开存档流程（依 Config 为槽位或自由存档） |
| `[load]` | 打开读档流程 |

玩家也可通过 **系统菜单 → 存档** 操作（`_template` 已汉化菜单项）。

---

## 7. 常用 TJS 表达式（嵌入剧本）

在 `[emb exp="..."]` 或 `@` 宏中可用：

| 表达式 | 含义 |
|--------|------|
| `System.title` | 窗口标题 |
| `kagVersion` | KAG 版本字符串 |
| `System.versionString` | 吉里吉里版本 |
| `f.变量名` / `sf.变量名` | 游戏变量（sf 为持久化） |

---

## 8. 与本仓库 system 的对应

| 需求 | 修改位置 |
|------|----------|
| 键位、分辨率、存档槽数 | `data/system/Config.tjs` |
| 菜单文字 | `data/system/Menus.tjs` |
| 对话框样式 | `data/system/MessageLayer.tjs` |
| 确认框 | `data/system/YesNoDialog.tjs` |

详见 [Config-常用项.md](Config-常用项.md) 与 [KAG3 键鼠操作（官方）](https://krkrz.github.io/krkr2doc/kag3doc/contents/MouseKeyboard.html)。
