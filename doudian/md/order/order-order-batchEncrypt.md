# order.batchEncrypt

> 批量加密接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.batchEncrypt` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/batchEncrypt` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/487 |
| 更新日期 | `2026-08-21` |

## 接口说明

- 文档书: 订单API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `batch_encrypt_list` | body | array | 是 | 待加密列表 | `` |
| `  └ plain_text` | body | string | 是 | 明文 | `13117428564` |
| `  └ is_support_index` | body | boolean | 是 | 是否支持密文索引 | `true` |
| `  └ sensitive_type` | body | mixed | 是 | 加密类型；1地址加密 2姓名加密 3电话加密 | `3` |
| `  └ auth_id` | body | string | 是 | 业务标识，value为抖音订单号；若是三方订单，可用三方订单号作为标识或自定义标识 | `123` |
| `sensitive_scene` | body | string | 否 | 加密场景：OrderCode代表订单 AftersaleCode代表售后单 | `OrderCode` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/batchEncrypt?app_key=your_appkey_here&method=order.batchEncrypt&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `encrypt_infos` | array | 加密之后的数据 | `-` |
| `custom_err` | object | 业务错误 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_err": {
      "err_code": "0",
      "err_msg": "-"
    },
    "encrypt_infos": [
      {
        "auth_id": "42341234171232",
        "cipher_text": "asdfasdfsasfdasdf",
        "decrypt_text": "13117428564",
        "err_msg": "-",
        "err_no": "0"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
