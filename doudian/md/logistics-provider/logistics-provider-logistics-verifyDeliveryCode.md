# 核销寄件码

> logistics.verifyDeliveryCode — 核销寄件码

| 元信息 | 值 |
| --- | --- |
| 中文名 | 核销寄件码 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-verifyDeliveryCode` |
| 接口 ID | `doudian.logistics-provider.logistics.verifyDeliveryCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/verifyDeliveryCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2936 |
| 更新日期 | `2026-10-13` |

## 接口说明

- 文档书: 物流商API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bizType` | body | string | 是 | 业务类型； 枚举：COURIER_STATION--驿站寄件 | `COURIER_STATION` |
| `orderId` | body | string | 是 | 订单号 | `LFO12345678904567` |
| `deliveryCode` | body | string | 是 | 寄件码 | `6472` |
| `operationTime` | body | string | 是 | 操作时间（格式：yyyy-MM-dd HH:mm:ss，24小时制） | `2021-01-19 15:12:23` |
| `partnerCode` | body | string | 是 | 服务商编码 | `yuantong` |
| `postCode` | body | string | 是 | 驿站编码 | `xx` |
| `postName` | body | string | 是 | 驿站名称 | `xxx` |
| `brandCode` | body | string | 是 | 品牌编码 | `mamayizhan` |
| `latitude` | body | string | 否 | 核销现场纬度，GCJ-02，6 位小数，与 longitude 成对可选 | `30.123456` |
| `longitude` | body | string | 否 | 核销现场经度，GCJ-02，6 位小数，与 latitude 成对可选 | `120.123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/verifyDeliveryCode?app_key=your_appkey_here&method=logistics.verifyDeliveryCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `errCode` | string | 失败原因编码（处理成功默认回传“0”） | `0` |
| `errReason` | string | 失败原因描述 | `核销成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10001） | 修改请求参数 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10002） | 接口重试 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10003） | 联系开发人员 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10101） | 订单不存在 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10102） | 订单已取消 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10201） | 当前状态不支持核销寄件码 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10202） | 寄件码错误 |
| `50002` | 业务处理失败 / 11017:数据库并发（sub_code: isv.business-failed:11017） | 11017:数据库并发 |
| `50002` | 业务处理失败 / 数据库异常（sub_code: isv.business-failed:11001） | 联系开发人员 |

## 响应示例

成功：

```json
{
  "data": {
    "errCode": "0",
    "errReason": "核销成功"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10001",
  "sub_msg": "-"
}
```

## 备注
