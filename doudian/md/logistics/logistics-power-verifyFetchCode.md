# 取件码核销（仅用于兼容老物流网关

> power.verifyFetchCode — 取件码核销（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 取件码核销（仅用于兼容老物流网关 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-verifyFetchCode` |
| 接口 ID | `doudian.logistics.power.verifyFetchCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/verifyFetchCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1478 |
| 更新日期 | `2026-10-26` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 商家订单号(下单接口传给物流服务商的orderId) | `4732078173688851864` |
| `waybill_code` | body | string | 否 | 运单号 | `JT0101001010` |
| `verify_code` | body | string | 否 | 取件码 | `6472` |
| `operate_time` | body | string | 否 | 核销操作时间 | `2021-01-19 15:12:23` |
| `longitude` | body | string | 否 | 经度 | `112.338589` |
| `latitude` | body | string | 否 | 纬度 | `16.830871` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/verifyFetchCode?app_key=your_appkey_here&method=power.verifyFetchCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11410:取件码错误（sub_code: isv.business-failed:11410） | 联系技术定位 |
| `50002` | 业务处理失败 / 11411:重复核销（sub_code: isv.business-failed:11411） | 不需要核销 |
| `50002` | 业务处理失败 / 11413:取消后不支持核销（sub_code: isv.business-failed:11413） | 无法核销 |
| `50002` | 业务处理失败 / 10002:当前状态不允许核销取件码（sub_code: isv.business-failed:10002） | 无法核销 |
| `50002` | 业务处理失败 / 11715:当前状态已取消不允许更新（sub_code: isv.business-failed:11715） | 无法核销 |
| `50002` | 业务处理失败 / 10000:不存在对应的取件信息（sub_code: isv.business-failed:10000） | 10000:不存在对应的取件信息 |
| `50002` | 业务处理失败 / 11412:运单号错误（sub_code: isv.business-failed:11412） | 无法核销 |
| `50002` | 业务处理失败 / 10010:物流商错误（sub_code: isv.business-failed:10010） | 无法核销 |

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
  "sub_code": "isv.business-failed:11410",
  "sub_msg": "11410:取件码错误"
}
```

## 备注
