# 获取视频详情

> 按视频 ID 拉取单条视频的详情数据（标题、作者、统计等）。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `douyin.video.detail` |
| 平台 | `douyin` |
| 请求方法 | `GET` |
| 接口路径 | `/aweme/v1/web/aweme/detail` |
| Base URL | `https://www.douyin.com` |
| 鉴权方式 | `cookie+sign` |
| 文档来源 | 自测整理（示例数据，字段以实测为准） |
| 更新日期 | `2026-11-04` |

## 接口说明

- 签名参数 a_bogus 由前端 JS 生成，过期或缺失会返回风控码。
- 高频调用易触发风控，建议控制频率并复用会话。

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aweme_id` | query | string | 是 | 视频 ID | `7xxxxx9000000000000` |
| `a_bogus` | query | string | 是 | 前端签名参数 | `Hh8XXXXXXXXX` |
| `device_platform` | query | string | 否 | 设备平台标识 | `webapp` |

## 请求示例

```bash
curl -X GET 'https://www.douyin.com/aweme/v1/web/aweme/detail?aweme_id=7xxxxx9000000000000&a_bogus=Hh8XXXXXXXXX&device_platform=webapp' -H 'Cookie: ttwid=<TTWID>' -H 'User-Agent: <UA>'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `0` | 成功 | 正常读取 aweme_detail 字段 |
| `2154` | 视频不存在或已删除 | 确认 aweme_id 后跳过 |
| `8` | 签名校验失败 | 重新生成 a_bogus 再试 |
| `cursor_out_of_range` | 风控拦截 | 降低频率，更换会话后重试 |

## 响应示例

成功：

```json
{
  "status_code": 0,
  "aweme_detail": {
    "aweme_id": "7xxxxx9000000000000",
    "desc": "示例视频标题",
    "author": {
      "nickname": "示例作者",
      "sec_uid": "MS4wLjABAAAAxxxxxxxx"
    },
    "statistics": {
      "digg_count": 12345,
      "comment_count": 678,
      "share_count": 90
    }
  }
}
```

失败：

```json
{
  "status_code": 8,
  "status_msg": "签名校验失败",
  "aweme_detail": null
}
```

## 备注
