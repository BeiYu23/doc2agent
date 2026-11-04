# 末端服务短信待发（仅用于兼容老物流网关

> power.sendByteDanceMessage — 末端服务短信待发（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 末端服务短信待发（仅用于兼容老物流网关 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-sendByteDanceMessage` |
| 接口 ID | `doudian.logistics.power.sendByteDanceMessage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/sendByteDanceMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1559 |
| 更新日期 | `2021-12-27` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 否 | - | `0` |
| `express_company` | body | string | 否 | - | `0` |
| `message` | body | string | 否 | - | `0` |
| `pick_msg_code` | body | string | 否 | - | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/sendByteDanceMessage?app_key=your_appkey_here&method=power.sendByteDanceMessage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11003:系统异常（sub_code: isv.business-failed:11003） | 11003:系统异常 |
| `50002` | 业务处理失败 / 11009:手机号不存在（sub_code: isv.business-failed:11009） | 11009:手机号不存在 |
| `50002` | 业务处理失败 / 11001:数据库异常（sub_code: isv.business-failed:11001） | 11001:数据库异常 |
| `50002` | 业务处理失败 / 11022:判断是否抖音包裹异常:网络超时（sub_code: isv.business-failed:11022） | 11022:判断是否抖音包裹异常:网络超时 |
| `50002` | 业务处理失败 / 11021:判断是否抖音面单异常:系统异常（sub_code: isv.business-failed:11021） | 11021:判断是否抖音面单异常:系统异常 |
| `50002` | 业务处理失败 / 11019:收件人信息获取失败:系统异常（sub_code: isv.business-failed:11019） | 11019:收件人信息获取失败:系统异常 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.business-failed:11003",
  "sub_msg": "11003:系统异常"
}
```

## 备注
