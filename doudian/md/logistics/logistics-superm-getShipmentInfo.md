# superm.getShipmentInfo

> 小时达运力平台运力配送状态查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.superm.getShipmentInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/getShipmentInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2743 |
| 更新日期 | `2023-09-19` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | number | 是 | 店铺父订单号 | `4993668078886578045` |
| `aftersale_id` | body | number | 否 | 上门取运力对应售后单号 | `3668078886578045` |
| `shipment_type` | body | string | 是 | 配送类型，1 表示发货单，需要传入店铺订单号 2 表示上门取件，需要传入店铺订单号和售后单编号 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/status?app_key=your_appkey_here&method=shop.status&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shipment_info` | object | 配送状态信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法的请求参数（sub_code: isv.parameter-invalid:40100） | 请确认请求参数是否正确 |
| `50002` | 业务处理失败 / 查询不到对应的物流订单（sub_code: isv.business-failed:20111） | 请确认订单状态是否正常 |
| `20000` | 系统错误（sub_code: isp.service-error:20100） | 请参考错误信息解决 |
| `50002` | 业务处理失败 / 物流轨迹展示异常（sub_code: isv.business-failed:20115） | 请参考物流轨迹展示异常信息 |
| `20001` | 内部服务超时 / 未知服务异常（sub_code: isp.service-timeout-error:90000） | 请参考错误信息解决 |
| `50002` | 业务处理失败 / 物流履约单当前状态无法取消运力信息（sub_code: isv.business-failed:50312） | 请确认运单状态 |
| `20000` | 系统错误 / 系统异常：系统异常（sub_code: isp.service-error:20201） | 请检查代码逻辑 |
| `50002` | 业务处理失败 / 请输入正确的订单号（sub_code: isv.business-failed:100009） | 请输入正确的订单号 |
| `50002` | 业务处理失败 / 订单不是该店铺下的订单，无权查询（sub_code: isv.business-failed:70009） | 订单不是该店铺下的订单，无权查询 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:20113） | 系统异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_status": {
      "shop_status": "9 初始化"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "非法的请求参数"
}
```

## 备注
