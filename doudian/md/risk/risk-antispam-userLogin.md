# antispam.userLogin

> 商户登陆风险检查

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.risk.antispam.userLogin` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/antispam/userLogin` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/187/635 |
| 更新日期 | `2021-06-28` |

## 接口说明

- 文档书: 风控安全API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user` | body | object | 否 | 用户 | `-` |
| `  └ uid_type` | body | string | 否 | 用户类型 | `12` |
| `  └ user_id` | body | number | 否 | 用户 ID | `12345` |
| `params` | body | string | 是 | 可变参数 | `{"account_id":12345}` |
| `event_time` | body | number | 否 | 事件时间 | `12345677` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/antispam/userLogin?app_key=your_appkey_here&method=antispam.userLogin&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `decision` | object | 决策 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -1:invalid request params: Read: unexpected value type: 0, error found in #7 byte of ...\|{"aid":云小叶}\|..., bigger context ...\|{"aid":云小叶}\|...（sub_code: isv.business-failed:-1） | -1:invalid request params: Read: unexpected value type: 0, error found in #7 byte of ...\|{"aid":云小叶}\|..., bigger context ...\|{"aid":云小叶}\|... |

## 响应示例

成功：

```json
{
  "data": {
    "decision": {
      "decision": "BLOCK",
      "decision_detail": "Too many incorrect attempts",
      "hit_status": "hit"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "-1:invalid request params: Read: unexpected value type: 0, error found in #7 byte of ...|{\"aid\":云小叶}|..., bigger context ...|{\"aid\":云小叶}|..."
}
```

## 备注
