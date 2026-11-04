# 查询任务发送情况

> sms.audience.getSendExecuteReport — 查询任务发送情况

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询任务发送情况 |
| 文档地址 | `/docs/doudian/sms/sms-sms-audience-getSendExecuteReport` |
| 接口 ID | `doudian.sms.sms.audience.getSendExecuteReport` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/getSendExecuteReport` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/6665 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `send_task_id` | body | string | 是 | 发送任务ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.getSendExecuteReport&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | object | 结果 | `` |
| `code` | mixed | 响应码 | `响应码` |
| `message` | string | 响应信息 | `响应信息` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少参数（sub_code: isv.missing-parameter:628002001） | 请检查入参 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "响应码",
    "message": "响应信息",
    "result": {
      "success_bill_count": "2",
      "success_count": "1",
      "total_count": "12"
    }
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:628002001",
  "sub_msg": "缺少参数"
}
```

## 备注
