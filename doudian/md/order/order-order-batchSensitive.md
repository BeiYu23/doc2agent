# order.batchSensitive

> 批量脱敏接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.batchSensitive` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/batchSensitive` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/508 |
| 更新日期 | `2021-07-14` |

## 接口说明

- 文档书: 订单API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cipher_infos` | body | array | 是 | 待脱敏的密文列表，每次调用不超过50条 | `` |
| `  └ auth_id` | body | string | 是 | 业务标识，value为抖音订单号 | `123` |
| `  └ cipher_text` | body | string | 是 | 密文 | `待脱敏密文，具体内容参考[数据安全加密对接文档](https://op.jinritemai.com/docs/guide-docs/56/589)` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/batchSensitive?app_key=your_appkey_here&method=order.batchSensitive&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `decrypt_infos` | array | 脱敏信息列表 | `-` |
| `custom_err` | object | 业务错误 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误: 输入的密文列表过长，上限为:50（sub_code: isv.parameter-invalid:100000） | 解密数据不要超出50 |
| `50002` | 业务处理失败 / 参数错误: 输入的密文列表过长，上限为:50（sub_code: isv.business-failed:300001） | 列表数据不要超过50 |
| `50002` | 业务处理失败 / 300003:参数错误: 输入的密文列表过长，上限为:50（sub_code: isv.business-failed:300003） | 300003:参数错误: 输入的密文列表过长，上限为:50 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_err": {
      "err_code": "错误码",
      "err_msg": "错误描述"
    },
    "decrypt_infos": [
      {
        "auth_id": "123",
        "cipher_text": "密文，具体内容参考[数据安全加密对接文档](https://op.jinritemai.com/docs/guide-docs/56/589)",
        "decrypt_text": "明文",
        "err_msg": "错误描述",
        "err_no": "错误码"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:100000",
  "sub_msg": "参数错误: 输入的密文列表过长，上限为:50"
}
```

## 备注
