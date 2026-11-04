# 获取商品sku列表

> sku.list — 获取商品sku列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取商品sku列表 |
| 文档地址 | `/docs/doudian/product/product-sku-list` |
| 接口 ID | `doudian.product.sku.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/82 |
| 更新日期 | `2026-08-28` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 否 | 商品ID；抖店系统生成。 | `3213654123157` |
| `out_product_id` | body | mixed | 否 | 外部商品ID；商家创建商品时自定义。 | `243523452435` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/list?app_key=your_appkey_here&method=sku.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | sku列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 5:[product_id]或[out_product_id]为0（sub_code: isv.business-failed:5） | 检查参数 |
| `40002` | 缺少必选参数 / [product_id]与[out_product_id]参数至少传一个（sub_code: isv.missing-parameter:3） | 检查参数 |
| `40004` | 非法的参数 / 该商品不属于你（sub_code: isv.parameter-invalid:4） | 检查参数 |
| `50002` | 业务处理失败 / 获取库存数失败（sub_code: isv.business-failed:7） | 检查参数 |
| `50002` | 业务处理失败 / 获取总店店铺标签失败（sub_code: isv.business-failed:2010001） | 检查参数 |
| `50002` | 业务处理失败 / 请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 限流，稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "channel_stock_num": "11",
        "code": "dy001",
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
          "usage": "品牌"
        },
        "gift_suit_detail": [
          {
            "name": {
              "unit": "无",
              "value": "开心果"
            },
            "net_content": {
              "unit": "g",
              "value": "50"
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
        "id": "1736402086955032",
        "is_suit": "0",
        "multi_time_stocks": [
          {
            "stock_num": "500",
            "time_desc": "5天内发",
            "time_type": "5"
          }
        ],
        "normal_stock_num": "11",
        "open_user_id": "0",
        "out_sku_id": "0",
        "prehold_step_stock_num": "20",
        "prehold_stock_map": {},
        "prehold_stock_num": "50",
        "price": "12",
        "product_id": "3557453527615939930",
        "product_id_str": "3557453527615939930",
        "prom_step_stock_num": "100",
        "prom_stock_num": "50",
        "sell_properties": [
          {
            "value_name": "红色",
            "value_spec_detail_id": "111"
          }
        ],
        "settlement_price": "12",
        "ship_rule_map": {},
        "sku_status": "true",
        "sku_type": "0",
        "spec_detail_id1": "1737037851057159",
        "spec_detail_id2": "0",
        "spec_detail_id3": "0",
        "spec_detail_name1": "默认",
        "spec_detail_name2": "\"\"",
        "spec_detail_name3": "\"\"",
        "spec_id": "1737037851056167",
        "step_stock_num": "100",
        "stock_map": {},
        "stock_num": "100",
        "suit_num": "0",
        "supplier_id": "333",
        "volume": "0"
      }
    ]
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
  "sub_code": "isv.business-failed:5",
  "sub_msg": "5:[product_id]或[out_product_id]为0"
}
```

## 备注
