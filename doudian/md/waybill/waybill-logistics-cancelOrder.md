# logistics.cancelOrder

> 用于ISV/商家ERP系统 端发起取消已获取的电子面单号；
面单有任何物流轨迹之后不允许取消。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.cancelOrder` |
| 中文名 | 用于ISV/商家ERP系统 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/cancelOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/397 |
| 更新日期 | `2021-04-22` |

## 接口说明

- 文档书: 电子面单API（版本 V1.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 是 | 物流公司 | `jd` |
| `track_no` | body | string | 是 | 运单号 | `1234` |
| `user_id` | body | number | 否 | 实际使用取号服务店铺user_id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/cancelOrder?app_key=your_appkey_here&method=logistics.cancelOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cancel_result` | object | 取消状态 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 轨迹存在（sub_code: isv.business-failed:10902） | 无 |
| `50002` | 业务处理失败 / 错误：该运单号3180437295999已经有物流信息,不能取消（sub_code: isv.business-failed:10804） | 无 |
| `50002` | 业务处理失败 / 物流商系统无此运单，无法取消（sub_code: isv.business-failed:10803） | 无 |
| `50002` | 业务处理失败 / 该运单已取件，不允许取消（sub_code: isv.business-failed:10802） | 无 |
| `40004` | 非法的参数 / 电子面单号不存在（sub_code: isv.parameter-invalid:10014） | 输入正确的运单号 |
| `50002` | 业务处理失败 / 取消总数/取号总数超过最大比例（sub_code: isv.business-failed:10013） | 无 |
| `40004` | 非法的参数 / 该数据不存在，请检查后重试（sub_code: isv.parameter-invalid:10003） | 无 |
| `50002` | 业务处理失败 / 此订单已收件（sub_code: isv.business-failed:8060） | 无 |
| `40004` | 非法的参数 / 该物流商暂不支持取消面单号（sub_code: isv.parameter-invalid:5001） | 无 |
| `50002` | 业务处理失败 / 订单已发货，取消面单号失败（sub_code: isv.business-failed:4007） | 无 |
| `50002` | 业务处理失败 / 已经取消过了，无需再次取消（sub_code: isv.business-failed:10901） | 无 |
| `50002` | 业务处理失败 / 该运单已取消成功,请勿重复操作（sub_code: isv.business-failed:10801） | 无 |
| `40002` | 缺少必选参数 / 物流单号不能为空（sub_code: isv.missing-parameter:400） | 输入运单号 |
| `20000` | 系统错误 / 系统错误或此状态不允许取消（sub_code: isp.service-error:10002） | 无 |
| `20000` | 系统错误 / 请求物流服务商超时（sub_code: isp.service-error:4009） | 进行重试 |
| `50002` | 业务处理失败 / 已消单（sub_code: isv.business-failed:8037） | 无 |
| `50002` | 业务处理失败 / 10903:单号已回收，不允许变更（sub_code: isv.business-failed:10903） | 无 |
| `50002` | 业务处理失败 / 20001:重复请求（sub_code: isv.business-failed:20001） | 无 |
| `20000` | 系统错误 / 4001（sub_code: isp.service-error:4001） | 系统内部错误，可以先进行重试处理，如果多次重试失败，开发者交流群进行反馈 |
| `20000` | 系统错误 / 11404:系统异常（sub_code: isp.service-error:11404） | 系统内部错误，可以先进行重试处理，如果多次重试失败，开发者交流群进行反馈 |
| `50002` | 业务处理失败 / 10000:该运单已取件，不允许取消（sub_code: isv.business-failed:10000） | 无 |
| `20000` | 系统错误 / 4008:内部数据JSON/XML格式非法（sub_code: isp.service-error:4008） | 一般都是物流商导致的原因，比如超时或物流商服务返回的有问题 |
| `50002` | 业务处理失败 / 8018:未获取到订单信息（sub_code: isv.business-failed:8018） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 1105:已揽收，无法取消（sub_code: isv.business-failed:1105） | 无 |
| `50002` | 业务处理失败 / 10724:取消失败，如果有疑问请联系京东大件物流（sub_code: isv.business-failed:10724） | 如果有疑问请联系京东大件物流 |
| `50002` | 业务处理失败 / 20802:该运单已取件，不允许取消（sub_code: isv.business-failed:20802） | 无 |
| `50002` | 业务处理失败 / 10711:电子面单订购关系不存在（sub_code: isv.business-failed:10711） | 请检查订购关系是否正常 |
| `50002` | 业务处理失败 / 1102:重复取消（sub_code: isv.business-failed:1102） | 无 |
| `50002` | 业务处理失败 / 10805:揽收后且派送前的单子才可拦截（sub_code: isv.business-failed:10805） | 10805:揽收后且派送前的单子才可拦截 |
| `50002` | 业务处理失败 / 200201:此订单已收件（sub_code: isv.business-failed:200201） | 200201:此订单已收件 |
| `50002` | 业务处理失败 / 10912:更新失败（sub_code: isv.business-failed:10912） | 10912:更新失败 |
| `50002` | 业务处理失败 / 14003:电子面单号取消失败（sub_code: isv.business-failed:14003） | 14003:电子面单号取消失败 |
| `50002` | 业务处理失败 / -10007:biz error: http client请求返回值非200（sub_code: isv.business-failed:-10007） | -10007:biz error: http client请求返回值非200 |
| `50002` | 业务处理失败 / 9999:已发货不能取消（sub_code: isv.business-failed:9999） | 9999:已发货不能取消 |
| `50002` | 业务处理失败 / 10010:系统异常（sub_code: isv.business-failed:10010） | 10010:系统异常 |

## 响应示例

成功：

```json
{
  "data": {
    "cancel_result": {
      "success": "true"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10902",
  "sub_msg": "轨迹存在"
}
```

## 备注
