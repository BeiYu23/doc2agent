# sms.sendSmsByTask

> 通过父任务发起新的短信发送任务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sendSmsByTask` |
| 中文名 | 通过父任务发起新的短信发送任务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sendSmsByTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7789 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `audience_send_task_id` | body | mixed | 否 | 短信发送任务id, /sms/audience/send的响应参数 | `123` |
| `part_send_config` | body | object | 否 | 入参 | `` |
| `  └ target_send_count` | body | mixed | 否 | 目标发送数量，优先级较高 | `123` |
| `  └ target_send_percent` | body | mixed | 否 | 目标发送百分比范围(0,100]，若目标发送数量>0，则以目标发送数量为准 | `34` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sendSmsByTask?app_key=your_appkey_here&method=sms.sendSmsByTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sub_task_id` | string | 子任务id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "sub_task_id": "123"
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
