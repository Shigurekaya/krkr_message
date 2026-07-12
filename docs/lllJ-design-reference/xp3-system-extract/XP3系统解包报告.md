# lllJ 系统 XP3 自动化解包报告

> 生成：2026-07-12  
> 方法：KrkrzExtract 注入 + 标题待机（无游戏内 UI 操作）+ hash 映射 tamago 静态解密 + yuzuex 文本解码

## 1. 流程（无需人工切换游戏界面）

```
KrkrzExtract.exe + limelight_lj.exe
    → 自动点击 Begin Extraction（Win32 ctypes）
    → 游戏停在标题/启动阶段 ~30s（自动加载系统资源）
    → krkrz_dump/ 输出已解密文件（当前 474 个）

并行静态解密（不依赖 XP3 拖放）：
    krkrz_dump 文件名/大小 ↔ XP3 adler32 hash
    → tamago 按 hash 打开 uipsd / image / data 成员
    → 输出 tamago-recovered/
```

**说明**：向 KrkrzExtract 窗口拖放 `.xp3` 在 64 位环境下几乎无效（+0~1 文件）。实际有效路径是 **hook 后 dump + hash 映射 tamago**。

## 2. 解包结果

| 包 | 索引条目 | hash 映射 | tamago 解密成功 |
|----|----------|-----------|-----------------|
| uipsd.xp3 | 175 | 81 | 81 |
| image.xp3 | 99 | 18 | 18 |
| data.xp3 | 1835 | 254 | 254 |
| **合计** | — | **353** | **353** |

另从 `krkrz_dump` 直接复制系统相关文件 **333** 个到 `files/`（含运行时解密的 yuzuex 文本）。

## 3. 编码处理（Shift-JIS / UTF-8 冲突）

lllJ 文本表（`help_*.txt`、`uitexts.toml`、`charlist.csv` 等）使用 **yuzuex 容器**：

| 特征 | 值 |
|------|-----|
| 魔数 | `FE FE 01 FF FE` |
| 正文 | **UTF-16-LE**，头部后需 **skip 6–13** 字节对齐（非 UTF-8） |
| 误用 cp932 直接解 | 会产生乱码 |
| tamago 静态提取的同名文件 | 常为密文，**应优先使用 krkrz_dump 版本** |

解码统计（`decode-report.json`）：

- `utf-16-le/yuzuex@*`：**52** 个文件已转为 UTF-8 文本 → `decoded-text/*.utf8.txt`
- `cp932`：**1** 个（混合表）
- `binary`：**26** 个（TJS2100 字节码等，需字符串抽取）

## 4. 目录结构

```
xp3-system-extract/
├── pipeline-summary.json      # 总统计
├── hash-path-map.json         # XP3 hash → 文件名
├── tamago-extract-result.json # 逐文件解密结果
├── tamago-recovered/          # tamago 解出的 XP3 成员（按包分目录）
├── files/                     # 合并后的系统文件（dump 优先）
├── decoded-text/              # yuzuex/文本 UTF-8 解码结果
└── auto-extract.log           # 运行日志
```

## 5. 重新执行

```powershell
cd D:\gamedev\GAL框架\tools\lllj-extract

# 1) 注入 hook（标题待机 30s，无游戏内操作）
.\.venv\Scripts\python.exe -c "import subprocess,time; from auto_system_xp3_pipeline import *; kill_all(); time.sleep(1); subprocess.Popen([str(EXTRACTOR),str(GAME_EXE)],cwd=str(GAME)); time.sleep(10); dlg=find_dialog_hwnd(); user32.SendMessageW(find_button(dlg,'Begin Extraction'),BM_CLICK,0,0); time.sleep(30); kill_all(); print(count_files(DUMP))"

# 2) hash 映射 + tamago 解密 + 文本解码
.\.venv\Scripts\python.exe auto_system_xp3_pipeline.py --skip-hook

# 3) 更新系统设计文档
.\.venv\Scripts\python.exe extract_system_design.py
```

## 6. 限制

- **未全量解 data.xp3**（1835 条中解出 254 + dump 重叠部分）；其余需更多运行时加载或已知虚拟路径
- **PSD 原图** 仍多在加密包内；dump 以 PBD/TLG 布局为主
- **scn.xp3** 剧本未纳入（非系统 UI 目标）
