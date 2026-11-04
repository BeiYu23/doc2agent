# logistics.terminalCancelOrder

> 物流商取消

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.terminalCancelOrder` |
| 中文名 | 物流商取消 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/terminalCancelOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2032 |
| 更新日期 | `2024-03-01` |

## 接口说明

- 文档书: 物流发货API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybillCode` | body | string | 否 | 运单号 | `12345677` |
| `orderId` | body | string | 否 | 订单号 | `lfo1234567` |
| `operationType` | body | string | 否 | 取消类型 | `1` |
| `backCode` | body | string | 否 | 取回码 | `1234` |
| `operatorName` | body | string | 否 | 操作人姓名 | `张三` |
| `operatorTel` | body | string | 否 | 操作人号码 | `12345678` |
| `cancelCode` | body | string | 否 | 取消编码 | `1234` |
| `cancelReason` | body | string | 否 | 取消原因 | `柜子无货` |
| `isConnected` | body | boolean | 否 | 是否接通 | `true` |
| `call` | body | boolean | 否 | 是否电联 | `true` |
| `callNums` | body | string | 否 | 电联次数 | `2` |
| `callInfo` | body | array | 否 | 电联明细 | `` |
| `  └ callNumber` | body | string | 否 | 电联号码（快递员） | `15161052766` |
| `  └ callerName` | body | string | 否 | 电联人姓名（快递员） | `张三` |
| `  └ receiveNumber` | body | string | 否 | 用户号码 | `15161052766` |
| `  └ isConnected` | body | boolean | 否 | 是否接通 | `true` |
| `  └ callTime` | body | string | 否 | 电联时间 | `2021-01-19 10:00:00` |
| `  └ callDuration` | body | string | 否 | 通话时长 | `10` |
| `needConnect` | body | boolean | 否 | 是否需要电联 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 修改参数 |
| `20000` | 系统错误 / 订单不存在（sub_code: isp.service-error:11005） | 联系技术 |
| `20000` | 系统错误 / 状态机初始化失败（sub_code: isp.service-error:12001） | 联系技术 |
| `20000` | 系统错误 / 当前状态不允许取消（sub_code: isp.service-error:12002） | 联系技术 |
| `20000` | 系统错误 / mq异常（sub_code: isp.service-error:11002） | 可重试 |
| `20000` | 系统错误 / 数据库异常（sub_code: isp.service-error:11001） | 可重试 |
| `20000` | 系统错误 / 并发异常（sub_code: isp.service-error:11017） | 可重试 |
| `50002` | 业务处理失败 / 支付成功29天后不允许取消（sub_code: isv.business-failed:14001） | 联系技术 |
| `50002` | 业务处理失败 / 不满足电联条件（sub_code: isv.business-failed:14002） | 请电联 |
| `50002` | 业务处理失败 / 用户未还款不允许取消（sub_code: isv.business-failed:14003） | 通知用户还款 |
| `50002` | 业务处理失败 / 11003:系统异常（sub_code: isv.business-failed:11003） | 11003:系统异常 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误"
}
```

## 备注
