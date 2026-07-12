# lllJ 设计参考包

静态分析 `E:\GAL\lllJ` + `krkrz_dump` 运行时解包，用于学习 UI/立绘/SD/转场/表情的**设计与插入方式**（非素材抄袭）。

## 快速入口

- **[设计管线参考.md](./设计管线参考.md)** — 主文档，必读
- **[system-design/系统性设计提取报告.md](./system-design/系统性设计提取报告.md)** — UI/流程图/表情/转场/鉴赏 结构化提取
- **[xp3-system-extract/XP3系统解包报告.md](./xp3-system-extract/XP3系统解包报告.md)** — 自动 hook + hash 映射 tamago 解密 + yuzuex 文本解码
- **[asset-catalog-from-save.json](./asset-catalog-from-save.json)** — 2664 CG ID、569 SD ID、设置 autotrail 等
- **[manifest.json](./manifest.json)** — 提取统计

## 目录

```
lllJ-design-reference/
├── README.md
├── 设计管线参考.md
├── manifest.json
├── asset-catalog-from-save.json
├── system-design/           # 系统性设计提取（2026-07-12）
│   ├── 系统性设计提取报告.md
│   ├── ui-architecture.json
│   ├── flowchart-architecture.json
│   ├── expression-system.json
│   ├── transition-system.json
│   ├── gallery-system.json
│   ├── tjs-analysis/
│   ├── pbd-analysis/
│   └── data-analysis/
├── krkrz_dump/              # 设计相关运行时解包文件
├── scripts/
│   └── startup.tjs          # TJS2100 启动字节码（唯一明文脚本）
├── savedata/                # 全 CG 存档 + 解码
└── indexes/                 # XP3 文件 hash/大小目录
```

## 重新生成

```powershell
# 静态索引 + 存档解码
cd D:\gamedev\GAL框架\tools\lllj-extract
.\.venv\Scripts\python.exe build_design_reference.py

# 系统性设计提取（需先有 krkrz_dump）
.\.venv\Scripts\python.exe extract_system_design.py

# 自动 hook + XP3 hash 解密 + 文本解码（见 xp3-system-extract/XP3系统解包报告.md）
.\.venv\Scripts\python.exe auto_system_xp3_pipeline.py --skip-hook

# 同步 krkrz_dump 到参考包
.\copy_krkrz_dump.ps1
```

## 限制

- XP3 内 PSD/TLG/大部分 TJS **文件体加密**，静态无法导出图片
- csv/txt/toml 等数据表为 yuzuex 打包格式，仅可抽字符串
- 文件名表混淆；路径靠存档 ID 与索引 hash 推断
- 语音/BGM 未收录
