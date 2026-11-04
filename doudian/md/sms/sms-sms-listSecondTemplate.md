# sms.listSecondTemplate

> 获取二级模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.listSecondTemplate` |
| 中文名 | 获取二级模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/listSecondTemplate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8436 |
| 更新日期 | `2026-07-28` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | string | 否 | 一级模板id | `S1T_xxx` |
| `signature_list` | body | array | 否 | 签名列表 | `["111", "22"]` |
| `sub_account` | body | string | 否 | 消息组 | `sofe` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillReturn?app_key=your_appkey_here&method=iop.waybillReturn&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | object | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "982734",
    "pack_list": [
      {
        "company_code": "jd",
        "deliver_id": "982734",
        "ship_num": "1",
        "track_no": "12345"
      }
    ],
    "return_result": "true"
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
