# douyin 接口目录

> 全平台 1 个接口。文档地址均为**本仓库内相对路径**（`md/` 人读版 + `agent/` 机器读版成对）。

| 接口 ID | 名称 | 方法 | 路径 | 分组 | 人读文档 | 机器读文档 |
| --- | --- | --- | --- | --- | --- | --- |
| `douyin.video.detail` | 获取视频详情 | `GET` | `/aweme/v1/web/aweme/detail` | - | [`md`](../douyin/md/video-detail.md) | [`json`](../douyin/agent/video-detail.json) |

## 用法

- Agent 先读 `catalog/index.json` 拿平台清单，再读对应 `catalog/<platform>.json` 按 id 定位接口。
- 每个接口的两份文档路径在 `md` / `agent` 字段里直接给出，无需拼接。
- 接口的**官方来源 URL** 在各接口 `agent/<...>.json` 的 `source` 字段。
