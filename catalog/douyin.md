# douyin 接口目录

> 全平台 1 个接口。首列 `中文名` 可直接点击跳转到该接口文档（`docUrl` 为前端站内路由）；`md` / `agent` 为**本仓库内相对路径**，成对。

| 中文名 | 文档地址 | 接口 ID | 名称 | 方法 | 路径 | 分组 | 人读文档 | 机器读文档 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [获取视频详情](/docs/douyin/video-detail) | `/docs/douyin/video-detail` | `douyin.video.detail` | 获取视频详情 | `GET` | `/aweme/v1/web/aweme/detail` | - | [`md`](../douyin/md/video-detail.md) | [`json`](../douyin/agent/video-detail.json) |

## 用法

- 前端：读 `catalog/<platform>.json`，把 `cnName` 作为显示名、`docUrl` 作为跳转目标（`/docs/<platform>/<group>/<stem>`）。
- Agent：先读 `catalog/index.json` 拿平台清单，再读对应 `catalog/<platform>.json` 按 `cnName` / `id` 定位接口。
- 每个接口的仓库内两份文档路径在 `md` / `agent` 字段里直接给出，无需拼接。
- 接口的**官方来源 URL** 在各接口 `agent/<...>.json` 的 `source` 字段；`docUrl` 是站内路由，不是官方 URL。
