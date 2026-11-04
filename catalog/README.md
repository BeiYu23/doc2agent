# catalog —— 全平台接口目录

这里放**所有接口**：首字段是中文名，附前端可跳转的 `docUrl` 与**本仓库内**的文档地址（`md/` 人读 + `agent/` 机器读，成对）。

## 文件

- `index.json` —— 全平台总索引（平台名 → 清单文件 → 接口数）
- `<platform>.json` —— 平台接口清单，条目字段按 `cnName / docUrl / id / name / method / path / description / group / md / agent` 排列
- `<platform>.md` —— 人读表格版：首列中文名可直接点击跳转

## 前端 / Agent 读取顺序

1. `catalog/index.json` → 拿到平台与清单文件路径
2. `catalog/<platform>.json` → 按 `cnName` / `id` 检索接口
3. 前端用 `docUrl`（`/docs/<platform>/<group>/<stem>`）作为跳转目标；`cnName` 作显示名
4. 直接取条目的 `md` / `agent` 相对路径打开对应文档（无需再查 `<platform>/agent/index.json`）

## 约定

- `docUrl` 是**前端站内路由**，不是官方文档站 URL；`md` / `agent` 是仓库内相对路径。
- 官方来源 URL 保留在各接口 `agent/<group>/<api>.json` 的 `source` 字段。
- `docUrl` 与 md/agent 文件名一一对应（含冲突消解的 `-k2` 后缀），由 `gen.py` 统一生成。
- 本目录由 `tool/gen_catalog.py` 从各平台 `agent/index.json` 生成，**勿手改**；
  平台文档刷新后重跑 `python cli.py catalog` 即可。
