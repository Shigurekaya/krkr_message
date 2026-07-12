# Config.tjs 常用项

> 配置文件路径：`projects/<作品>/data/system/Config.tjs`  
> 模板内已有 **逐行中文注释**；本页为开发者速查索引。  
> 修改后需重启游戏；部分项可在运行时由菜单覆盖（会写入系统变量文件）。

语法：每项一行 `;变量名 = 值;`（分号开头为 Config 脚本约定，不是注释忽略）。

---

## 1. 全局

| 配置项 | 说明 | 模板默认参考 |
|--------|------|--------------|
| `System.title` | 窗口标题、任务栏名称 | `;System.title = "GAL 框架";` |
| `global.ignoreCR` | 剧本换行是否当作显示换行 | `true`（KAG3 标准） |
| `System.graphicCacheLimit` | 图像缓存上限 | `gcsAuto` |

---

## 2. 窗口与存档

| 配置项 | 说明 |
|--------|------|
| `scWidth` / `scHeight` | 画面宽高（像素） |
| `readOnlyMode` | 只读模式（禁止写存档，如 CD 运行） |
| `freeSaveDataMode` | `false`=槽位存档；`true`=自由文件存档 |
| `saveThumbnail` | 存档是否保存缩略图 |
| `thumbnailWidth` | 缩略图宽度 |
| `numBookMarks` | 可用存档槽数量 |
| `saveDataLocation` | 存档目录名（相对 dataPath） |

---

## 3. 文字与自动播放

| 配置项 | 说明 |
|--------|------|
| `defaultChSpeed` | 默认文字显示速度（毫秒/字） |
| `autoModePageWait` | 自动播放时页末等待（毫秒） |
| `autoModeLineWait` | 自动播放时行末 `[l]` 等待（毫秒） |
| `chSpeeds.*` | 菜单中「高速 / 普通 / 慢速」等预设 |

---

## 4. 菜单栏显示（`_template` 已汉化文案）

在 `KAGWindow_config()` 内，控制各菜单项是否可见：

| 配置项 | 对应菜单（模板中文） |
|--------|----------------------|
| `rightClickMenuItem.visible` | 系统 → 清除对话框 |
| `showHistoryMenuItem.visible` | 系统 → 显示对话履历 |
| `autoModeMenuItem.visible` | 系统 → 自动播放 |
| `goBackMenuItem.visible` | 系统 → 回退 |
| `goToStartMenuItem.visible` | 系统 → 回到开头 |
| `restoreMenu.visible` | 存档 → 读取存档 |
| `storeMenu.visible` | 存档 → 保存存档 |
| `menu.visible` | 是否显示整个菜单栏 |

发行 Gal 时常关闭 `menu.visible`，改用游戏内 UI（参见 KAG3_Ham 或自绘界面）。

---

## 5. 消息层（对话框）

| 配置项 | 说明 |
|--------|------|
| `userFace` / `deffont` 相关 | 默认字体（模板含微软雅黑、黑体） |
| `userFontSize` | 字号 |
| `userFontColor` | 文字颜色 |
| `marginL/T/R/B` | 消息层四边距 |
| `vertical` | 竖排模式 |
| `lineBreakGlyph` / `pageBreakGlyph` | 点击等待标记图像名 |

---

## 6. 对话履历

| 配置项 | 说明 |
|--------|------|
| `historyStoreMax` | 履历保留条数上限 |
| `historyBookMarkStore` | 存档是否包含履历 |

---

## 7. Ham 扩展（仅 KAG3_Ham）

在 `[start-global-additionals]` 块内：

| 配置项 | 说明 |
|--------|------|
| `global.useHamExtention` | `true` 启用 Ham 图形 UI |

启用后加载 `system/Ham/Ham.tjs`；布局与颜色见 `Ham/Preferences.tjs`。  
详见 [KAG3_Ham-说明.md](KAG3_Ham-说明.md)。

---

## 8. 修改流程建议

1. 复制 `_template` 或 `init-project.ps1` 新建项目。  
2. 只改 `projects/<名>/data/system/Config.tjs`，勿改 `engine/` 子模块。  
3. KAG 版本升级时，若提示 Config 过期，由 `UpdateConfig.tjs` 合并旧设置。  
4. 键位与滚轮行为见 `Config.tjs` 内注释，或 [KAG3 键鼠操作（官方）](https://krkrz.github.io/krkr2doc/kag3doc/contents/MouseKeyboard.html)。

---

## 9. 官方文档

Config 全部字段以模板文件内注释为准；标签与 system 行为对照 [KAG3 在线文档（原文日文）](https://krkrz.github.io/krkr2doc/kag3doc/contents/index.html)。
