# instantShopping.distributionMerchant.statusCallback

> 配送商状态回调

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.instantShopping.distributionMerchant.statusCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/6516 |
| 更新日期 | `2024-05-14` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orderId` | body | string | 否 | 抖音呼单id | `"1"` |
| `tradeOrderId` | body | string | 否 | 抖音即配运单id | `"1"` |
| `carrierDeliveryId` | body | string | 否 | 物流单号 | `"1"` |
| `status` | body | mixed | 否 | 状态 https://bytedance.larkoffice.com/wiki/QzSAwROIxiQNQPkLD20cxp2mnbe | `1` |
| `riderName` | body | string | 否 | 上报骑手姓名 | `"王晓"` |
| `riderId` | body | string | 否 | 骑手/司机Id，接单后必填 | `"1"` |
| `riderPhone` | body | string | 否 | 上报骑手电话。若使用隐私号，须确保商家和收件人在配送完成后48小时内均可通过该电话联系上骑手。 | `"13322224444"` |
| `riderPhoneType` | body | mixed | 否 | 骑手/司机电话类型。0：真实号 1：隐私号 | `1` |
| `riderPhoneExpire_time` | body | mixed | 否 | 隐私号距离完成单号失效时间，秒。骑手/司机的电话类型是隐私号时，该字段必填 | `1715686808` |
| `riderLng` | body | mixed | 否 | 骑手/司机经度*10^6 火星坐标系 | `122333333` |
| `riderLat` | body | mixed | 否 | 骑手/司机纬度*10^6 火星坐标系 | `122333333` |
| `operateTime` | body | mixed | 否 | 状态变更时间，秒时间戳 | `1715686808` |
| `cancelReasonCode` | body | mixed | 否 | 订单取消原因code https://bytedance.larkoffice.com/wiki/SHbHwg39ni3PLokoMQBceKAbnEf | `100` |
| `cancelSource` | body | mixed | 否 | 取消来源 https://bytedance.larkoffice.com/wiki/SHbHwg39ni3PLokoMQBceKAbnEf | `10` |
| `cancelReasonDesc` | body | string | 否 | 订单取消原因描述，订单为取消状态则必填 | `"1"` |
| `actualFee` | body | string | 否 | 实际支付金额，元 | `1` |
| `licenseplate` | body | string | 否 | 车牌号 | `"浙A3332"` |
| `orderImages` | body | string | 否 | 订单详情的Map信息（订单详情的Map信息，key是业务场景，value是照片的URL组合的List 图片最多不超过5张) | `{"业务场景":["url","url"]}` |
| `tollFee` | body | string | 否 | 过路费，包括高速费、过桥费等，元 | `1` |
| `handlingFee` | body | string | 否 | 搬运费，元 | `1` |
| `waitingFee` | body | string | 否 | 等候费，元 | `1` |
| `parkingFee` | body | string | 否 | 停车费，元 | `1` |
| `otherCharges` | body | string | 否 | 其他费用 | `{"其他费用":12}` |
| `extInfo` | body | string | 否 | 订单扩展信息，json格式，线下约定不同承运商的kv结构。 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/deliveryInfoNotify_uat?app_key=your_appkey_here&method=wms.deliveryInfoNotify_uat&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1101510032:transfer delivery DeliveryId is error（sub_code: isv.business-failed:1101510032） | 1101510032:transfer delivery DeliveryId is error |
| `50002` | 业务处理失败 / 100002006:获取分布式锁失败（sub_code: isv.business-failed:100002006） | 100002006:获取分布式锁失败 |
| `50002` | 业务处理失败 / 1454039998:服务异常，请稍后再试#（sub_code: isv.business-failed:1454039998） | 1454039998:服务异常，请稍后再试# |
| `50002` | 业务处理失败 / 999001001:订单扩展信息不能为空（sub_code: isv.business-failed:999001001） | 999001001:订单扩展信息不能为空 |
| `50002` | 业务处理失败 / 999002001:redis异常（sub_code: isv.business-failed:999002001） | 999002001:redis异常 |
| `50002` | 业务处理失败 / 1101510309:UpdateDelivery lock err（sub_code: isv.business-failed:1101510309） | 1101510309:UpdateDelivery lock err |
| `50002` | 业务处理失败 / 1101519998:服务异常，请稍后再试#（sub_code: isv.business-failed:1101519998） | 1101519998:服务异常，请稍后再试# |
| `50002` | 业务处理失败 / 100002007:数据InterfaceConf异常，缺失%!s(MISSING)（sub_code: isv.business-failed:100002007） | 100002007:数据InterfaceConf异常，缺失%!s(MISSING) |

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
  "sub_code": "isv.business-failed:1101510032",
  "sub_msg": "1101510032:transfer delivery DeliveryId is error"
}
```

## 备注
