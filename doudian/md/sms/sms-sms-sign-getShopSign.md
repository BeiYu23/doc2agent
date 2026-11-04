# 获取商家在抖店的最新审核通过签名

> sms.sign.getShopSign — 获取商家在抖店的最新审核通过签名

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取商家在抖店的最新审核通过签名 |
| 文档地址 | `/docs/doudian/sms/sms-sms-sign-getShopSign` |
| 接口 ID | `doudian.sms.sms.sign.getShopSign` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/getShopSign` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8148 |
| 更新日期 | `2026-03-24` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/getShopSign?app_key=your_appkey_here&method=sms.sign.getShopSign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `signature_info` | object | 签名信息 | `` |
| `message_group_info` | object | 消息组 | `` |
| `isv_available_sign_list` | array | 仅ISV专用消息组下的签名，sms_account=ISV消息组id | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "isv_available_sign_list": [
      {
        "apply_time": "1232312",
        "sign": "北京基石泰来",
        "sms_account": "osjfoae"
      }
    ],
    "message_group_info": {
      "default_message_group": "seofj",
      "isv_message_group": "osjfoae"
    },
    "signature_info": {
      "has_signature": "true",
      "signature_content": "基石泰来"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
