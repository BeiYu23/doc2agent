# 查询留言列表

> pigeon.getLeaveMsgList — 查询留言列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询留言列表 |
| 文档地址 | `/docs/doudian/feige/feige-pigeon-getLeaveMsgList` |
| 接口 ID | `doudian.feige.pigeon.getLeaveMsgList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getLeaveMsgList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5344 |
| 更新日期 | `2023-11-09` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `day_duration` | body | number | 是 | 查询近几天的留言列表：会有 1 7 15 30 这几个值 | `1` |
| `page` | body | number | 是 | 从0开始 | `1` |
| `page_size` | body | number | 是 | pageSize | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/getLeaveMsgList?app_key=your_appkey_here&method=pigeon.getLeaveMsgList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg_list` | array | 结果列表 | `` |
| `page` | number | page_no | `1` |
| `page_size` | number | page_size | `10` |
| `total` | number | 总记录数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "msg_list": [
      {
        "conversation_id": "324",
        "doudian_open_id": "34",
        "last_msg_time": "3313233",
        "leave_msg_id": "w34",
        "source": "1",
        "status": "1",
        "withdraw_status": "1"
      }
    ],
    "page": "1",
    "page_size": "10",
    "total": "10"
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
