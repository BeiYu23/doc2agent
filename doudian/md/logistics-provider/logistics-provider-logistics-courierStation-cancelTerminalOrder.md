# logistics.courierStation.cancelTerminalOrder

> 驿站主动取消订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.courierStation.cancelTerminalOrder` |
| 中文名 | 驿站主动取消订单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2938 |
| 更新日期 | `2023-04-03` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orderId` | body | string | 是 | 订单号 | `LFO12345678904567` |
| `cancelCode` | body | string | 是 | 取消/拦截原因编码（枚举值参考OPENAPI，联系对接研发） | `10815` |
| `cancelReason` | body | string | 否 | 取消/拦截原因描述 | `用户超时未支付` |
| `operationTime` | body | string | 是 | 操作时间（格式：yyyy-MM-dd HH:mm:ss，24小时制） | `2023-02-03 00:00:00` |
| `bizType` | body | string | 是 | 业务类型； 枚举：COURIER_STATION--驿站寄件 | `COURIER_STATION` |
| `partnerCode` | body | string | 是 | 服务商编码 | `yuantong` |
| `postCode` | body | string | 否 | 驿站编码 | `xx` |
| `postName` | body | string | 否 | 驿站名称 | `xxx` |
| `status` | body | string | 是 | 状态； 枚举：Canceled--取消，Intercepted--拦截 | `Canceled` |
| `brandCode` | body | string | 是 | 品牌编码 | `mamayizhan` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/inbound/cancel?app_key=your_appkey_here&method=yunc.wms.inbound.cancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `errCode` | string | 失败原因编码（处理成功默认回传“0”） | `0` |
| `errReason` | string | 失败原因描述 | `取消成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10001） | 修改请求参数 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10002） | 接口重试 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10003） | 联系开发人员 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10101） | 订单不存在 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10104） | 订单当前状态不允许取消 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10105） | 订单当前状态不允许拦截 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10110） | 不支持重复取消 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10111） | 不支持重复拦截 |
| `50002` | 业务处理失败 / 10207:取消失败，距离核销成功不满2天，不允许取消（sub_code: isv.business-failed:10207） | 10207:取消失败，距离核销成功不满2天，不允许取消 |
| `50002` | 业务处理失败 / 11017:数据库并发（sub_code: isv.business-failed:11017） | 11017:数据库并发 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
