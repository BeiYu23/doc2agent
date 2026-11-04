# yunc.CloudCreateOutboundOrderToB

> 云仓出库接单toB

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.CloudCreateOutboundOrderToB` |
| 中文名 | 云仓出库接单toB |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/CloudCreateOutboundOrderToB` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1198 |
| 更新日期 | `2021-09-17` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 否 | 仓编码 | `1` |
| `in_warehouse_code` | body | string | 是 | 入库仓库 | `99` |
| `delivery_mode` | body | string | 是 | 交货方式 | `1` |
| `erp_order_no` | body | string | 是 | ERP出库单号 | `1234234` |
| `order_type` | body | string | 是 | 订单类型 | `1` |
| `expected_qty` | body | string | 是 | 应发数量 | `100` |
| `source_platform_code` | body | string | 是 | 订单来源平台编码 | `2222` |
| `source_platform_name` | body | string | 是 | 订单来源平台名称 | `德化仓` |
| `order_time` | body | number | 是 | 前台订单下单时间 | `1612202522000` |
| `review_time` | body | number | 是 | 审单时间 | `1612202522000` |
| `express_code` | body | string | 是 | 快递公司编码 | `shunfeng` |
| `express_name` | body | string | 否 | 快递公司名称 | `顺丰` |
| `is_insure` | body | string | 是 | 是否保价 | `1` |
| `insure_amount` | body | string | 否 | 保价金额 | `1000` |
| `express_product_id` | body | string | 否 | 快递产品类型 | `shunfeng001` |
| `express_product_name` | body | string | 否 | 快递产品名称 | `顺丰次日达` |
| `shop_id` | body | number | 是 | 店铺id | `2345` |
| `shop_name` | body | string | 是 | 店铺名 | `1` |
| `allow_merge` | body | string | 是 | 是否允许合单 | `1` |
| `sender_info` | body | object | 是 | 发件人信息 | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ province` | body | string | 是 | 省份名称 | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `002` |
| `  └ city` | body | string | 是 | 城市名称 | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `003` |
| `  └ district` | body | string | 是 | 地区名称 | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `004` |
| `  └ street` | body | string | 否 | 街道名称 | `闲林街道` |
| `  └ detail` | body | string | 是 | 详细地址 | `西溪八方城` |
| `  └ name` | body | string | 是 | 姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 联系方式 | `15677711111` |
| `  └ tel_phone` | body | string | 否 | 固定电话 | `15677711111` |
| `receiver_info` | body | object | 是 | 收件人信息 | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ province` | body | string | 否 | 省份名称 | `合肥省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `001` |
| `  └ city` | body | string | 否 | 城市名称 | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `001` |
| `  └ district` | body | string | 否 | 地区名称 | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `001` |
| `  └ street` | body | string | 否 | 街道名称 | `西溪八方城` |
| `  └ detail` | body | string | 否 | 地址 | `北京` |
| `  └ name` | body | string | 否 | 姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 手机 | `15677711111` |
| `  └ tel_phone` | body | string | 否 | 电话 | `15677711111` |
| `remark` | body | string | 否 | 备注 | `轻拿轻放` |
| `buyer_message` | body | string | 否 | 买家备注 | `放门口` |
| `seller_message` | body | string | 否 | 卖家备注 | `贵重物品` |
| `order_details` | body | array | 是 | 订单详情 | `` |
| `  └ line_no` | body | string | 是 | 出库单行号 | `22323` |
| `  └ cargo_code` | body | string | 否 | 平台货品编码 | `23232` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品编码 | `23234234` |
| `  └ sku_name` | body | string | 是 | 商品名称 | `鲜花` |
| `  └ expected_qty` | body | string | 是 | 订单数量 | `12` |
| `  └ inventory_type` | body | string | 是 | 库存类型 | `1` |
| `  └ inventory_status` | body | string | 是 | 库存状态 | `1` |
| `  └ barcode` | body | string | 否 | 货品条码 | `23423423` |
| `  └ category_name` | body | string | 否 | 类目名称 | `服饰` |
| `  └ product_date` | body | number | 否 | 生产日期 | `1612202522000` |
| `  └ expire_date` | body | number | 否 | 过期日期 | `1612202522000` |
| `  └ batch_code` | body | string | 否 | 批次号 | `1` |
| `owner_code` | body | string | 否 | 货主编码 | `1` |
| `extend` | body | string | 否 | 扩展字段 | `{key:val}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/CloudCreateOutboundOrderToB?app_key=your_appkey_here&method=yunc.CloudCreateOutboundOrderToB&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
  },
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
