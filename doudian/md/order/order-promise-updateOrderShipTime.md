# promise.updateOrderShipTime

> 更新订单承诺发货时间

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.promise.updateOrderShipTime` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/promise/updateOrderShipTime` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7857 |
| 更新日期 | `2025-11-10` |

## 接口说明

- 文档书: 订单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `scene` | body | mixed | 是 | 更新场景，枚举值如下： AppleUpdateShipTime = 1 苹果更新发货时效 | `1` |
| `shop_order_id` | body | string | 是 | 店铺单id | `6943784145523119325` |
| `sku_order_update_info_list` | body | array | 是 | sku单更新信息 | `` |
| `  └ sku_order_id` | body | string | 是 | sku单id | `6943784145523119325` |
| `  └ ship_time` | body | mixed | 是 | 需要更新的发货时间（秒级时间戳） | `1762790399` |
| `extra_info` | body | string | 否 | 额外信息 | `<"key":"value">` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/promise/updateOrderShipTime?app_key=your_appkey_here&method=promise.updateOrderShipTime&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误：ShopOrderId不能为空（sub_code: isv.parameter-invalid:501） | 正确传入ShopOrderId |

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
  "sub_code": "isv.parameter-invalid:501",
  "sub_msg": "参数错误：ShopOrderId不能为空"
}
```

## 备注
