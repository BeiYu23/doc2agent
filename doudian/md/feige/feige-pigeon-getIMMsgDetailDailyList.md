# 查询消息列表

> pigeon.getIMMsgDetailDailyList — 查询消息列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询消息列表 |
| 文档地址 | `/docs/doudian/feige/feige-pigeon-getIMMsgDetailDailyList` |
| 接口 ID | `doudian.feige.pigeon.getIMMsgDetailDailyList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getIMMsgDetailDailyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5348 |
| 更新日期 | `2025-07-24` |

## 接口说明

- 文档书: 飞鸽API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `conv_ids` | body | array | 是 | 会话id列表,单次不能超过100 | `7300859031382394152` |
| `date` | body | string | 是 | 会话开始时间所在的日期 | `20231102` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/getIMMsgDetailDailyList?app_key=your_appkey_here&method=pigeon.getIMMsgDetailDailyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `i_m_msg_details` | array | 消息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 最多只能查询35天的数据（sub_code: isv.business-failed:1000） | 最多只能查询35天的数据 |

## 响应示例

成功：

```json
{
  "data": {
    "i_m_msg_details": [
      {
        "auto_welcome_tag": "1",
        "card_type": "live_invitation",
        "content_type": "transfer_conversation",
        "conv_id": "7293093180768109839",
        "direction": "1",
        "direction_v2": "1",
        "doudian_open_id": "1",
        "msg_type": "1",
        "phase": "1",
        "robot_auto_answer": "1",
        "send_time_ts": "1",
        "server_msg_id": "1",
        "sponsor": "1",
        "staff_id": "1",
        "trans_in_staff_id": "1"
      }
    ]
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1000",
  "sub_msg": "最多只能查询35天的数据"
}
```

## 备注
