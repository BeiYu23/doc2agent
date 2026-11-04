# pigeon.ISVEvaluationCallback

> ISV评测结果回调接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.service.pigeon.ISVEvaluationCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/ISVEvaluationCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1532/7840 |
| 更新日期 | `2026-03-31` |

## 接口说明

- 文档书: 三方客服API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `evaluation_data_json` | body | string | 否 | 回调参数，需要包含推送接口的完整内容并加入output | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/ISVEvaluationCallback?app_key=your_appkey_here&method=pigeon.ISVEvaluationCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否成功 | `true` |
| `message` | string | 响应消息 | `"Callback processed successfully"` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "message": "\"Callback processed successfully\"",
    "success": "true"
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
