# sku.stockNum

> 查询商品规格库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.sku.stockNum` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/stockNum` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/936 |
| 更新日期 | `2025-02-17` |

## 接口说明

- 文档书: 库存API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_id` | body | mixed | 否 | 商品规格id，店铺商品id下唯一，抖店平台生成 | `12345` |
| `code` | body | string | 否 | sku商家编码，对应抖店后台商品sku商家编码。外部开发者自定义商品规格id，会校验在店铺下唯一性 | `abc` |
| `out_warehouse_id` | body | string | 否 | 仓库编码（供应商编码） | `AN871` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/stockNum?app_key=your_appkey_here&method=sku.stockNum&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sku_id` | mixed | 商品规格id，店铺商品id下唯一，抖店平台生成 | `12345` |
| `out_sku_id` | mixed | 外部开发者自定义商品规格id，会校验再店铺下唯一性 | `12345` |
| `code` | string | sku商家编码，对应抖店后台商品sku商家编码 | `abc` |
| `sku_type` | mixed | sku库存类型，0-普通库存；1-区域库存；10-阶梯库存； | `0` |
| `stock_num` | mixed | 商品规格库存；如果sku_type=0，表示全国库存； 如果sku_type=1，且入参有out_warehouse_id，则表示该仓库的库存； 如果sku_type=1，且入参无out_warehouse_id，则为空； | `12` |
| `prehold_stock_num` | mixed | 占用库存 | `12` |
| `prom_stock_num` | mixed | 活动库存 | `12` |
| `step_stock_num` | mixed | 阶梯库存 | `12` |
| `prehold_step_stock_num` | mixed | 阶梯占用库存 | `12` |
| `prom_step_stock_num` | mixed | 活动阶梯库存 | `12` |
| `stock_num_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为库存 | `1` |
| `prehold_stock_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为占用库存 | `1` |
| `ship_rule_map` | string | 如果sku_type=0，为空 如果sku_type=1，则为区域仓库存映射表，key为out_warehouse_id，value为sku在仓中的发货时效 | `` |
| `normal_stock_num` | mixed | 普通库存，非活动可售 | `1` |
| `channel_stock_num` | mixed | 渠道库存 | `1` |
| `batch_stocks` | array | 批次库存 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / code: 195250981220, 找不到对应的sku（sub_code: isv.parameter-invalid:20050） | 请检查参数后重试 |
| `40004` | 非法的参数 / 参数不合法: 请输入正确sku_id或sku_code（sub_code: isv.parameter-invalid:20011） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品信息获取异常: 获取库存数失败（sub_code: isv.business-failed:20100） | 请稍后重试 |
| `50002` | 业务处理失败 / 2010004:code: 4550583951313, 找不到对应的sku（sub_code: isv.business-failed:2010004） | 2010004:code: 4550583951313, 找不到对应的sku |
| `50002` | 业务处理失败 / 2010001:查询关联productId信息失败（sub_code: isv.business-failed:2010001） | 2010001:查询关联productId信息失败 |
| `50002` | 业务处理失败 / 20053:读取商品失败（sub_code: isv.business-failed:20053） | 20053:读取商品失败 |

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
    "channel_stock_num": "1",
    "code": "abc",
    "normal_stock_num": "1",
    "out_sku_id": "12345",
    "prehold_step_stock_num": "12",
    "prehold_stock_map": {},
    "prehold_stock_num": "12",
    "prom_step_stock_num": "12",
    "prom_stock_num": "12",
    "ship_rule_map": {},
    "sku_id": "12345",
    "sku_type": "0",
    "step_stock_num": "12",
    "stock_num": "12",
    "stock_num_map": {}
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
  "sub_msg": "code: 195250981220, 找不到对应的sku"
}
```

## 备注
