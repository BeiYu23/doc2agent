# doc2agent

各网站 / 平台接口文档仓库。文档直接以 git 管理，人读的 Markdown 与 AI 读的 JSON 双轨并行、同一接口一一对应。

## 目录结构

```
doc2agent/
├── _templates/          # 统一格式模板（新增接口时从这里复制）
│   ├── api-template.md  #   人读版模板
│   └── api-template.json#   agent 版模板
├── catalog/             # 全平台接口总目录：所有接口 + 本仓库内文档地址
│   ├── index.json       #   全平台总索引
│   ├── <platform>.json  #   平台清单（机器读）
│   └── <platform>.md    #   平台清单（人读表格）
├── douyin/              # 抖音（实测整理，CURATED 清单生成）
│   ├── md/
│   └── agent/
├── doudian/             # 抖店（开放平台文档站全量抓取，1504 唯一接口，按书分组）
│   ├── md/<book>/       #   按文档书分组：order / product / shop / ...
│   └── agent/<book>/    #   同名成对的 JSON + _common.json 公共参数 + index.json
├── ...                  # 新平台照此模式建目录
└── tool/                # 抓取/生成/校验代码（本地维护，不提交）
```

- 每个平台一个顶层目录，平台目录下固定分 `md/` 与 `agent/` 两条路径。
- `md/` 放人读的 Markdown；`agent/` 放机器可读的 JSON，同名文件一一对应（`video-detail.md` ↔ `video-detail.json`）。
- 接口多的平台按书/分组落子目录，`agent/index.json` 保留分组维度。
- 每个平台的 `agent/index.json` 是该平台接口索引，AI 从索引进入，再按 `id` 取具体接口。
- 所有接口使用统一格式，模板见 `_templates/`；格式演进以模板为准，存量文档随模板升级。

## 统一格式要点

- 接口元信息：`id`（平台.资源.动作）、平台、名称、方法、路径、鉴权。
- 请求参数：参数名 / 位置 / 类型 / 必填 / 说明 / 示例。
- 响应码：每个接口必须列出 `code` / 含义 / 处理建议。
- 示例：必须含请求示例 + 成功响应示例 + 失败响应示例。
- 来源与更新日期：注明文档出处链接与最后核对日期。

## 给 AI / Agent 的读取方式

1. 读 `catalog/index.json` 拿全平台清单，再读 `catalog/<platform>.json` 按 `id` 检索接口——条目直接给出本仓库内 `md` / `agent` 相对路径（**不是官方文档站 URL**）。
2. 也可读 `<platform>/agent/index.json` 获取单平台清单（id → 文件名 → 一句话说明）。
3. 按需读取 `<platform>/agent/<api>.json`，字段结构统一，见 `_templates/api-template.json`。
4. JSON 中所有字段自解释，无需解析 Markdown；需要给人看的上下文时再读对应 `md/` 文档。
5. 接口的官方来源 URL 保留在各接口 `agent/*.json` 的 `source` 字段。

## 接口目录（catalog）

- `catalog/` 由 `tool/gen_catalog.py` 从各平台 `agent/index.json` 生成，**勿手改**。
- 每个条目含 `id / cnName / name / method / path / group / description / md / agent` 九个字段（`cnName` 为从官方描述提炼的简短中文名）。
- 当前收录 1505 个接口（doudian 1504 + douyin 1）；平台文档刷新后跑 `python cli.py catalog` 重建。

## 新增接口流程

1. `cp _templates/api-template.md <platform>/md/<api>.md`，`cp _templates/api-template.json <platform>/agent/<api>.json`。
2. 按模板填写全部必填段（参数表、响应码表、请求与响应示例）。
3. 更新 `<platform>/agent/index.json` 加入新接口条目。
4. 提交：`git add . && git commit -m "docs(<platform>): add <api>"`。

## 约定

- 仓库内不提交 `AGENTS.md`、`todo.md`、`tool/`（见 `.gitignore`），它们是本地工作台文件。
- 接口文档必须成对出现：`md/` 与 `agent/` 同名同 id，缺一即视为不完整。
- 敏感信息（Cookie、Token、密钥）一律脱敏为占位符，禁止入库。
