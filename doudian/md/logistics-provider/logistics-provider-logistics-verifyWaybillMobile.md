# logistics.verifyWaybillMobile

> 验证运单收件人手机号与入参是否一致

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.verifyWaybillMobile` |
| 中文名 | 验证运单收件人手机号与入参是否一致 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/verifyWaybillMobile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/3514 |
| 更新日期 | `2023-04-21` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 是 | 运单号 | `7321234545` |
| `express_company` | body | string | 否 | 快递公司 | `shunfeng` |
| `mobile` | body | string | 是 | 手机号 | `xxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/verifyWaybillMobile?app_key=your_appkey_here&method=logistics.verifyWaybillMobile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_same` | boolean | 手机号是否一致 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / -（sub_code: isv.parameter-invalid:10001） | - |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10003） | - |

## 响应示例

成功：

```json
{
  "data": {
    "is_same": "true"
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
  "sub_code": "isv.parameter-invalid:10001",
  "sub_msg": "-"
}
```

## 备注
