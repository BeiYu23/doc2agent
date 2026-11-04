# yunc.createOutboundOrderToB

> toB出库单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.createOutboundOrderToB` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/createOutboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/927 |
| 更新日期 | `2023-01-18` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓编码 | `W001` |
| `in_warehouse_code` | body | string | 否 | 仓编码 | `W001` |
| `delivery_mode` | body | string | 是 | 运输方式：物流-1；快递-2；自提-3 | `1` |
| `erp_order_no` | body | string | 是 | erp单号 | `1111` |
| `order_type` | body | string | 是 | 调拨出库=2 退供出库=3 生产出库=5 其它出库=6 | `2` |
| `expected_qty` | body | string | 是 | 提货数量 | `11` |
| `source_platform_code` | body | string | 否 | 来源平台编码 | `543` |
| `source_platform_name` | body | string | 否 | 来源平台名称 | `543` |
| `order_time` | body | number | 是 | 订单时间 | `54345` |
| `review_time` | body | number | 否 | 审单时间 | `543454` |
| `express_code` | body | string | 否 | 快递公司编码 | `5434` |
| `express_name` | body | string | 否 | 快递公司名称 | `5454` |
| `is_insure` | body | string | 否 | 是否保价1=是0=否 | `1` |
| `insure_amount` | body | string | 否 | 快递产品类型 | `111` |
| `express_product_id` | body | string | 否 | 快递产品类型 | `111` |
| `express_product_name` | body | string | 否 | 快递产品名称 | `111` |
| `shop_id` | body | number | 是 | 店铺id（不强校验，填0即可） | `11111` |
| `shop_name` | body | string | 是 | 店铺名称（不强校验，填写“店铺”即可） | `11` |
| `allow_merge` | body | number | 是 | 是否允许合单 1=是 0=否 | `1` |
| `sender_info` | body | object | 否 | 省份编码 | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ province` | body | string | 是 | 省份 | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `11` |
| `  └ city` | body | string | 是 | 城市 | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `11` |
| `  └ district` | body | string | 否 | 地区 | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `11` |
| `  └ street` | body | string | 否 | 街道 | `大明街` |
| `  └ name` | body | string | 是 | 姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 手机号 | `11456789` |
| `  └ detail` | body | string | 是 | 详细地址 | `小红街道` |
| `receiver_info` | body | object | 是 | 省份编码 | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `11` |
| `  └ province` | body | string | 是 | 省份 | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `001` |
| `  └ city` | body | string | 否 | 城市 | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `002` |
| `  └ district` | body | string | 否 | 地区 | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `003` |
| `  └ street` | body | string | 否 | 街道 | `街` |
| `  └ name` | body | string | 是 | 姓名 | `李四` |
| `  └ mobile` | body | string | 否 | 手机号 | `54345654` |
| `  └ detail` | body | string | 是 | 详细地址 | `小绿` |
| `remark` | body | string | 否 | 留言 | `11` |
| `buyer_message` | body | string | 否 | 留言 | `留言` |
| `seller_message` | body | string | 否 | 留言 | `留言` |
| `extend` | body | string | 否 | 扩展 | `{"key":"val"}` |
| `order_details` | body | array | 是 | 出库单行号 | `` |
| `  └ line_no` | body | string | 是 | 出库单行号 | `45678` |
| `  └ inventory_type` | body | number | 是 | 库存类型 | `1` |
| `  └ inventory_status` | body | number | 是 | 库存状态 | `1` |
| `  └ barcode` | body | string | 否 | 货品条码 | `1111` |
| `  └ category_name` | body | string | 否 | 类目名称 | `名字` |
| `  └ cargo_code` | body | string | 否 | 平台货品编码 | `5454` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品编码 | `543454` |
| `  └ sku_name` | body | string | 是 | 商品名称 | `543454` |
| `  └ expected_qty` | body | number | 是 | 订单数量 | `11` |
| `  └ product_date` | body | number | 否 | 生产日期 | `54324` |
| `  └ expire_date` | body | number | 否 | 过期日期 | `54354` |
| `  └ batch_code` | body | string | 否 | 批次号 | `654354` |
| `owner_code` | body | string | 否 | 货主id | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/createOutboundOrderToB?app_key=your_appkey_here&method=yunc.createOutboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 62302609:下发仓储单据失败（sub_code: isv.business-failed:62302609） | 请重试！ |
| `50002` | 业务处理失败 / 10001:物流服务未开通（sub_code: isv.business-failed:10001） | 物流服务未开通 |

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
  "sub_code": "isv.business-failed:62302609",
  "sub_msg": "62302609:下发仓储单据失败"
}
```

## 备注
