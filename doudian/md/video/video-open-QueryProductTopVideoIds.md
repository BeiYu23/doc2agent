# open.QueryProductTopVideoIds

> 单商品 Top 内容 ID 查询接口协议

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.open.QueryProductTopVideoIds` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/QueryProductTopVideoIds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8641 |
| 更新日期 | `2026-09-21` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `content_type` | body | string | 否 | 内容体裁: 仅支持 video、image; video 返回短视频 ID, image 返回图文 item_id | `video` |
| `product_id` | body | string | 否 | 被查询的商品 ID(正 Int64 字符串) | `3000004973070000` |
| `time_range` | body | mixed | 否 | 统计窗口: 仅支持 1、7、30 | `7` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/QueryProductTopVideoIds?app_key=your_appkey_here&method=open.QueryProductTopVideoIds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 业务状态码, 成功为 0 | `0` |
| `message` | string | 成功时为 success | `success` |
| `data` | object | 业务数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "product_id": "3000004973070000",
      "top_video_ids": "[\"12333333\"]"
    },
    "message": "success"
  },
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
