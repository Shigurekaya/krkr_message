# krkr_message — krkrz / KAG 消息层与系统分析

> **给 AI / 新机器的入口文档**  
> 本仓库存放 krkrz 引擎汉化、KAG 系统脚本、以及 lllJ **系统层**运行时解包与分析（非 UI 专包）。

## 克隆后第一件事

```bash
git clone https://github.com/Shigurekaya/krkr_message.git
cd krkr_message
```

阅读顺序：

1. **本文（README）**
2. [`docs/lllJ-design-reference/README.md`](docs/lllJ-design-reference/README.md)
3. [`docs/lllJ-design-reference/设计管线参考.md`](docs/lllJ-design-reference/设计管线参考.md)
4. [`docs/汉化范围.md`](docs/汉化范围.md) — krkrz 汉化清单（**权威版本，gal- 仅为指针**）

配套仓库：

| 仓库 | 用途 |
|------|------|
| [LimeLight](https://github.com/Shigurekaya/LimeLight) | lllJ UI 反推（jp-ui-extract）、汉化 pck 元数据 |
| [gal-](https://github.com/Shigurekaya/gal-) | GAL 开发框架 |

---

## 本仓库独有内容（LimeLight 里没有）

| 路径 | 说明 |
|------|------|
| `docs/lllJ-design-reference/krkrz_dump/` | 运行时解包（设计相关子集，158 文件） |
| `docs/lllJ-design-reference/xp3-system-extract/` | XP3 系统归档自动解包 |
| `docs/lllJ-design-reference/system-design/` | UI/流程图/表情/转场结构化分析 |
| `kag/` | KAG 中文开发者文档（**最新版**） |
| `projects/_template/data/system/` | 汉化后的 KAG 系统脚本 |
| `docs/汉化范围.md` | 汉化范围权威文档 |

---

## 与 UI 反推的关系

- **标题/设置界面反推**：主材料在 **LimeLight** 的 `jp-ui-extract/`
- 本仓库的 `krkrz_dump/` 含 `title_jp.pbd`、`uitexts.toml` 等运行时明文，可作交叉验证
- `system-design/` 含消息层、对话框等系统性分析，补充 UI 反推

---

## 重新生成

```powershell
cd ../LimeLight/tools/lllj-extract   # 脚本在 LimeLight 仓库
python -m venv .venv
.\.venv\Scripts\pip install -r requirements.txt
python build_design_reference.py
python extract_system_design.py
```

---

## 注意

- `engine/` 子模块在 **gal-** 仓库，不在此库
- 游戏本体 `E:\GAL\lllJ\` 永不上传
