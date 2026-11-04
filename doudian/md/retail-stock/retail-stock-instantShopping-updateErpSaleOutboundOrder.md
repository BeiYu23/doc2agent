# 更新Erp订单关联的出库单状态

> instantShopping.updateErpSaleOutboundOrder — 更新Erp订单关联的出库单状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新Erp订单关联的出库单状态 |
| 文档地址 | `/docs/doudian/retail-stock/retail-stock-instantShopping-updateErpSaleOutboundOrder` |
| 接口 ID | `doudian.retail-stock.instantShopping.updateErpSaleOutboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1594/7647 |
| 更新日期 | `2025-08-06` |

## 接口说明

- 文档书: 库存管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outbound_order_id` | body | string | 是 | 抖音出库单号 | `"12312312312312"` |
| `outbound_order_status` | body | mixed | 是 | 销售出库单当前状态 | `120` |
| `update_time` | body | mixed | 是 | 状态更新时间 | `17098034222` |
| `operator_id` | body | string | 否 | 操作人id | `"8712368712638123"` |
| `operator_name` | body | string | 否 | 操作人姓名 | `"张三"` |
| `outbound_delivery_packs` | body | array | 否 | 包裹信息（城市仓200状态必传） | `` |
| `  └ delivery_pack_material_list` | body | array | 否 | 包裹耗材信息 | `` |
| `    └ material_code` | body | string | 否 | 耗材编码 | `123123123123` |
| `    └ delivery_pack_type` | body | mixed | 否 | 包裹类型，包材、耗材 | `1` |
| `    └ merchant_owned` | body | mixed | 否 | 是否商家自有，1 => 是，2 => 否 | `1` |
| `    └ usage_quantity` | body | mixed | 否 | 使用数量 | `11` |
| `  └ outbound_goods_detail` | body | array | 否 | 出库货品明细数据(200状态下必填) | `` |
| `    └ receive_time` | body | mixed | 否 | 入库日期(200状态下必填) | `1709803422` |
| `    └ expire_day` | body | mixed | 否 | 保质期(天)(200状态下必填) | `10` |
| `    └ production_time` | body | mixed | 否 | 生产日期(200状态下必填) | `1709803422` |
| `    └ outbound_count` | body | mixed | 否 | 数量(200状态下必填) | `1` |
| `    └ stock_type` | body | mixed | 否 | 库存类型(200状态下必填) 1: 正品 | `1` |
| `  └ outer_delivery_product_code` | body | string | 否 | 快递产品类型编码 | `01` |
| `  └ outer_delivery_id` | body | string | 否 | 快递运单号 | `SF123456789012` |
| `  └ outer_delivery_code` | body | string | 否 | 快递公司编码 | `shunfeng` |
| `  └ outbound_time` | body | mixed | 否 | 出库时间，秒级时间戳 | `1709803422` |
| `  └ delivery_pack_weight` | body | mixed | 否 | 包裹重量（单位：克） | `1000` |
| `  └ delivery_pack_volume` | body | mixed | 否 | 包裹体积（单位：立方厘米） | `1000` |
| `  └ delivery_pack_height` | body | mixed | 否 | 包裹高（单位：厘米） | `10` |
| `  └ delivery_pack_width` | body | mixed | 否 | 包裹宽（单位：厘米） | `q0` |
| `  └ delivery_pack_length` | body | mixed | 否 | 包裹长（单位：厘米） | `10` |
| `  └ delivery_pack_id` | body | string | 否 | 包裹号 | `51514312341251` |
| `erp_order_id` | body | string | 否 | erp单号 | `erp单号` |
| `warehosue_id` | body | string | 否 | 抖音仓id | `123123123123` |
| `warehouse_code` | body | string | 否 | 服务商仓code | `123123123123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.updateErpSaleOutboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:40001） | 传入合法入参 |
| `50002` | 业务处理失败 / 出库单不存在（sub_code: isv.business-failed:40004） | 传入正确的出库单id |
| `40004` | 非法的参数 / 没有权限操作出库单（sub_code: isv.parameter-invalid:40006） | 传入正确的出库单ID |
| `50002` | 业务处理失败 / 子单信息写入失败，请稍后重试（sub_code: isv.business-failed:50020） | 子单信息写入失败，请稍后重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50002） | 业务处理失败 |

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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "非法参数"
}
```

## 备注
