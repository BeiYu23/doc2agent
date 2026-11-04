# 获取商品sku

> sku.detail — 获取商品sku详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取商品sku |
| 文档地址 | `/docs/doudian/product/product-sku-detail` |
| 接口 ID | `doudian.product.sku.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/566 |
| 更新日期 | `2026-08-28` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | mixed | 否 | sku id | `1234` |
| `code` | body | string | 否 | sku code | `cccc` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/detail?app_key=your_appkey_here&method=sku.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `id` | mixed | sku id | `1111` |
| `open_user_id` | mixed | app_key | `2222` |
| `out_sku_id` | mixed | 外部的skuId | `3333` |
| `product_id` | mixed | 商品ID | `4444` |
| `spec_detail_id1` | mixed | 第一级子规格 | `5555` |
| `spec_detail_id2` | mixed | 第二级子规格 | `0` |
| `spec_detail_id3` | mixed | 第三级子规格 | `0` |
| `spec_detail_name1` | string | 第一级子规格名 | `规格1` |
| `spec_detail_name2` | string | 第二级子规格名 | `规格2` |
| `spec_detail_name3` | string | 第三级子规格名 | `规格3` |
| `customs_report_info` | object | 海关申报要素 | `` |
| `price` | mixed | 价格 | `12` |
| `settlement_price` | mixed | 结算价格 | `12` |
| `spec_id` | mixed | 规格ID | `2333` |
| `create_time` | mixed | 创建时间 | `1621611875` |
| `code` | string | sku外部编码 | `cccc` |
| `sku_type` | mixed | 0-普通 1-区域库存 | `0` |
| `supplier_id` | string | 供应商ID | `333` |
| `stock_num` | mixed | sku_type=0时，表示库存数量 sku_type=1时，使用stock_map | `11` |
| `prehold_stock_num` | mixed | sku_type=0时，表示预占库存数量 sku_type=1时，使用prehold_stock_map | `11` |
| `prom_stock_num` | mixed | 活动库存 | `11` |
| `step_stock_num` | mixed | 阶梯库存 | `11` |
| `prehold_step_stock_num` | mixed | 预占阶梯库存 | `11` |
| `prom_step_stock_num` | mixed | 活动阶梯库存 | `11` |
| `stock_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为库存 | `无` |
| `prehold_stock_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为占用库存 | `无` |
| `product_id_str` | string | 商品 ID 字符串 | `111` |
| `ship_rule_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为sku 在对应仓中的发货时效 | `` |
| `is_suit` | mixed | 是否套装，0 否，1 是 | `1` |
| `suit_num` | mixed | 套装内数量 | `10` |
| `volume` | mixed | 容量单位ml，酒类专有 | `100` |
| `status` | mixed | sku状态：0有效，1无效 | `0` |
| `multi_time_stocks` | array | 时效库存 | `` |
| `batch_stocks` | array | 批次库存 | `` |
| `gift_suit_detail` | array | 礼盒明细品（子品）列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / code: 1715469761741840, 找不到对应的sku（sub_code: isv.parameter-invalid:20050） | 请检查参数后重试 |
| `40004` | 非法的参数 / 参数不合法: 请输入正确sku_id或sku_code（sub_code: isv.parameter-invalid:20011） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品信息获取异常: 获取sku仓时效失败（sub_code: isv.business-failed:20100） | 请稍后重试 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:2010004） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 读取商品失败（sub_code: isv.business-failed:20053） | 请检查参数后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "batch_stocks": [
      {
        "batch_stock_items": [
          {
            "batch_type": "1",
            "stock_num": "1",
            "unique_id": "\"356303487400309\""
          }
        ],
        "out_warehouse_id": "\"FOURPLTEST\""
      }
    ],
    "code": "cccc",
    "create_time": "1621611875",
    "customs_report_info": {
      "bar_code": "条形码",
      "first_measure_qty": "1",
      "first_measure_unit": "克",
      "g_model": "规格型号",
      "hs_code": "aa",
      "report_brand_name": "品牌",
      "report_name": "品名",
      "second_measure_qty": "2",
      "second_measure_unit": "克",
      "unit": "个",
      "usage": "用途"
    },
    "gift_suit_detail": [
      {
        "name": {
          "unit": "无",
          "value": "开心果"
        },
        "net_content": {
          "unit": "50",
          "value": "g"
        },
        "quantity": {
          "unit": "袋",
          "value": "2"
        },
        "total_net_content": {
          "unit": "g",
          "value": "100"
        }
      }
    ],
    "id": "1111",
    "is_suit": "1",
    "multi_time_stocks": [
      {
        "stock_num": "500",
        "time_desc": "5天内发",
        "time_type": "5"
      }
    ],
    "open_user_id": "2222",
    "out_sku_id": "3333",
    "prehold_step_stock_num": "11",
    "prehold_stock_map": {},
    "prehold_stock_num": "11",
    "price": "12",
    "product_id": "4444",
    "product_id_str": "111",
    "prom_step_stock_num": "11",
    "prom_stock_num": "11",
    "settlement_price": "12",
    "ship_rule_map": {},
    "sku_type": "0",
    "spec_detail_id1": "5555",
    "spec_detail_id2": "0",
    "spec_detail_id3": "0",
    "spec_detail_name1": "规格1",
    "spec_detail_name2": "规格2",
    "spec_detail_name3": "规格3",
    "spec_id": "2333",
    "status": "0",
    "step_stock_num": "11",
    "stock_map": {},
    "stock_num": "11",
    "suit_num": "10",
    "supplier_id": "333",
    "volume": "100"
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
  "sub_code": "isv.parameter-invalid:20050",
  "sub_msg": "code: 1715469761741840, 找不到对应的sku"
}
```

## 备注
