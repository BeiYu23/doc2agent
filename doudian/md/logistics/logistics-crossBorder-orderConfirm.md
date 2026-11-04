# crossBorder.orderConfirm

> 服务商接单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.crossBorder.orderConfirm` |
| 中文名 | 服务商接单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/orderConfirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/401 |
| 更新日期 | `2021-04-23` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `NBNXYB` |
| `order_id` | body | string | 是 | 字节电商平台的交易订单号 | `4752902481541269011` |
| `status` | body | string | 是 | 接单状态 | `0` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间 | `2020-12-15 17:20:46` |
| `error_info` | body | object | 否 | 接单失败 | `-` |
| `  └ error_code` | body | string | 否 | 错误码 | `1` |
| `  └ error_msg` | body | string | 否 | 错误信息 | `test` |
| `deliver_info` | body | object | 否 | 运单信息 | `-` |
| `  └ carrier` | body | string | 否 | 快递公司编码 | `yunda` |
| `  └ trans_no` | body | string | 否 | 运单号 | `123334543` |
| `  └ ship_address` | body | string | 否 | 发货地址 | `{"city":{"name":"仁川广域市","id":""},"detail":"仁川广域市西区正西津2路32"}` |
| `  └ waybill` | body | string | 否 | 电子面单url(pdf格式) | `https://sf6-ttcdn-tos.pstatp.com/obj/temai/%E6%96%87%E5%AD%97%E6%96%87%E7%A8%BF1.pdf` |
| `  └ product_num` | body | number | 否 | 商品件数 | `1` |
| `  └ mark` | body | string | 否 | 大头笔 | `YD` |
| `  └ delivery_name` | body | string | 否 | 发货人姓名 | `小明` |
| `  └ delivery_tel` | body | string | 否 | 发货人电话 | `13160111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/orderConfirm?app_key=your_appkey_here&method=crossBorder.orderConfirm&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单状态不支持当前行为，请刷新后重试（sub_code: isv.business-failed:1005） | 请检查订单状态 |
| `50002` | 业务处理失败 / 推送的物流状态不对，请查证后重试, 当前状态是 跨境履约单创建成功（sub_code: isv.business-failed:1004） | 请检查物流状态 |
| `50002` | 业务处理失败 / 请求太频繁（sub_code: isv.business-failed:1002） | 请稍后重试 |
| `50002` | 业务处理失败 / 1006:record not found（sub_code: isv.business-failed:1006） | 请检查后重试 |

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
  "sub_code": "isv.business-failed:1005",
  "sub_msg": "订单状态不支持当前行为，请刷新后重试"
}
```

## 备注
