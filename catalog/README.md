# catalog —— 全平台接口目录

这里放**所有接口**与它们在**本仓库内**的文档地址（`md/` 人读 + `agent/` 机器读，成对）。

## 文件

- `index.json` —— 全平台总索引（平台名 → 清单文件 → 接口数）
- `<platform>.json` —— 平台接口清单，每个条目含 `id / cnName / name / method / path / group / description / md / agent`
- `<platform>.md` —— 同内容的人读表格版（含「中文名」列）

## Agent 读取顺序

1. `catalog/index.json` → 拿到平台与清单文件路径
2. `catalog/<platform>.json` → 按 `id` / `cnName` / `name` 检索接口（`cnName` 是从官方描述提炼的简短中文名）
3. 直接取条目的 `md` / `agent` 相对路径打开对应文档（无需再查 `<platform>/agent/index.json`）

## 约定

- 目录里的地址是**仓库内相对路径**，不是官方文档站 URL。
- 官方来源 URL 保留在各接口 `agent/<group>/<api>.json` 的 `source` 字段。
- 本目录由 `tool/gen_catalog.py` 从各平台 `agent/index.json` 生成，**勿手改**；
  平台文档刷新后重跑 `python cli.py catalog` 即可。
