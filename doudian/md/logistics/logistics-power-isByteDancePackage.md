# power.isByteDancePackage

> 末端服务字节面单信息查询（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.isByteDancePackage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/isByteDancePackage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1558 |
| 更新日期 | `2025-04-17` |

## 接口说明

- 文档书: 物流发货API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 否 | - | `0` |
| `express_company` | body | string | 否 | - | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/isByteDancePackage?app_key=your_appkey_here&method=power.isByteDancePackage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_bytedance_waybill` | string | 是否是字节包裹 | `0` |
| `is_bytedance_dec` | string | 是否是字节面单 | `0` |
| `sender` | object | 寄件人信息 | `` |
| `receiver` | object | 收件人信息 | `` |
| `privacy_flag` | string | 是否是虚拟号 | `1` |
| `isSmsSupported` | boolean | 是否支持短信代发 | `true` |
| `smsNotSupportedReason` | string | 短信不支持原因 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11009:手机号不存在（sub_code: isv.business-failed:11009） | 修改入参 |
| `50002` | 业务处理失败 / 11004:不支持该物流服务商（sub_code: isv.business-failed:11004） | 修改入参 |
| `50002` | 业务处理失败 / 11000:expressCompany is nil（sub_code: isv.business-failed:11000） | 修改入参 |
| `50002` | 业务处理失败 / 11003:系统异常（sub_code: isv.business-failed:11003） | 重试 |
| `50002` | 业务处理失败 / 11021:判断是否抖音面单异常:不支持该物流服务商（sub_code: isv.business-failed:11021） | 11021:判断是否抖音面单异常:不支持该物流服务商 |
| `50002` | 业务处理失败 / 11022:判断是否抖音包裹异常:网络超时（sub_code: isv.business-failed:11022） | 11022:判断是否抖音包裹异常:网络超时 |
| `50002` | 业务处理失败 / 11019:收件人信息获取失败:网络超时（sub_code: isv.business-failed:11019） | 11019:收件人信息获取失败:网络超时 |

## 响应示例

成功：

```json
{
  "data": {
    "isSmsSupported": "true",
    "is_bytedance_dec": "0",
    "is_bytedance_waybill": "0",
    "privacy_flag": "1",
    "receiver": {
      "auth_end_time": "-",
      "auth_flag": "-",
      "auth_start_time": "-",
      "is_virtual_no": "0",
      "mobile": "0",
      "name": "0",
      "virtual_no": "0",
      "virtual_status": "0"
    },
    "sender": {
      "auth_end_time": "-",
      "auth_flag": "-",
      "auth_start_time": "-",
      "is_virtual_no": "0",
      "mobile": "0",
      "name": "0",
      "virtual_no": "0",
      "virtual_status": "0"
    },
    "smsNotSupportedReason": "-"
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
  "sub_code": "isv.business-failed:11009",
  "sub_msg": "11009:手机号不存在"
}
```

## 备注
