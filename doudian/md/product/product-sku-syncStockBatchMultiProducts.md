# sku.syncStockBatchMultiProducts

> 多商品内 sku 更新库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.sku.syncStockBatchMultiProducts` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/syncStockBatchMultiProducts` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2847 |
| 更新日期 | `2025-09-08` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `items` | body | array | 是 | 请求列表 | `` |
| `  └ store_code` | body | string | 否 | 相对于 store_id 是平台侧的门店 id，store_code 是外部门店编码，使用上，选择其中一个，优先使用 store_id | `123sdfaseq` |
| `  └ sku_code` | body | string | 否 | sku 商家编码，开发者在创建或更新商品时设置的，商家自行要保证一个商品下的所有 sku 编码唯一，否则通过 sku_code+商品 id 无法准确定位唯一的sku，会导致更新库存至非预期内的sku 上 | `123sdfaseq` |
| `  └ outer_product_id` | body | string | 否 | 外部商品id；开发者在创建或更新商品时设置的，是out_product_id的字符串形式 | `123sdfaseq` |
| `  └ store_id` | body | mixed | 否 | 即时零售小时达店铺更新配送门店商品库存，抖店自提店铺用于设置商品自提门店库存 | `12345` |
| `  └ out_sku_id` | body | mixed | 否 | 外部skuid，开发者在创建或更新商品时设置。 | `44354354` |
| `  └ out_product_id` | body | mixed | 否 | 外部商品id；开发者在创建或更新商品时设置的。 | `36116949497011600` |
| `  └ product_id` | body | mixed | 否 | 商品ID | `3587155767318456791` |
| `  └ sku_id` | body | mixed | 否 | 商品规格ID；一次请求最大支持50个sku更新 | `1751540901742600` |
| `  └ out_warehouse_id` | body | string | 否 | 外部仓库id编码，开发者自定义；如传入传值表示更新区域库存，不传默认更新普通库存。可以使用【/warehouse/list】接口响应参数【out_warehouse_id】字段获取。超市小时达店铺类型，需传入store_id字段，store_id可以使用【/shop/batchCreateStore】创建成功后获取 | `hh` |
| `  └ stock_num` | body | mixed | 否 | 现货库存数 | `1` |
| `  └ step_stock_num` | body | mixed | 否 | 阶梯库存数 | `2` |
| `  └ uniq_id` | body | string | 否 | 批量请求中item的唯一标识 | `uniqId1` |
| `idempotent_id` | body | string | 是 | 幂等ID，平台会校验校验成功的idempotent_id值，请保证24小时内在店铺下唯一性，建议使用年月日时分秒+随机数生成。重复的idempotent_id会触发“Token已被使用”报错 | `123k` |
| `incremental` | body | boolean | 是 | 库存更新方式，必填字段；true-增量更新，同时stock_num和step_stock_num字段可以为正数或负数；false-全量更新，同时stock_num和step_stock_num字段只能为正数数 | `true` |
| `source` | body | string | 否 | 请求来源，开发者自定义； | `123sdfaseq` |
| `allow_partial_success` | body | boolean | 否 | 是否允许部分成功失败，默认接口级别成功失败 | `false` |
| `inventory_loss` | body | boolean | 否 | 是否允许负库存 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/syncStockBatchMultiProducts?app_key=your_appkey_here&method=sku.syncStockBatchMultiProducts&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `results` | array | 结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（check not pass）（sub_code: isv.parameter-invalid:-30001） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 内部请求错误（sub_code: isv.business-failed:-5000） | 请稍后重试 |
| `50002` | 业务处理失败 / 商户状态不合法: 初始状态（sub_code: isv.business-failed:-40010） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 当前商户状态，不可编辑（sub_code: isv.business-failed:-40011） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品审核中，不可更新（sub_code: isv.business-failed:-40001） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品封禁，不可更新（sub_code: isv.business-failed:-40002） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品已删除，不可更新（sub_code: isv.business-failed:-40003） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 账号权限错误（sub_code: isv.business-failed:-40012） | 请检查参数后重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:-10002） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 设置库存逻辑错误（sub_code: isv.business-failed:-10007） | 请检查参数后重试 |
| `50002` | 业务处理失败 / Token已被使用（sub_code: isv.business-failed:-20002） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 库存不足（sub_code: isv.business-failed:-20001） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 有关联的货品，无法修改库存（sub_code: isv.business-failed:-20011） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 当前商品的部分SKU库存不得低于活动/达人专属价设置的库存数（sub_code: isv.business-failed:-20008） | 请检查参数后重试 |
| `50002` | 业务处理失败 / -10021:并发冲突, 请重试（sub_code: isv.business-failed:-10021） | 请稍后重试 |
| `50002` | 业务处理失败 / -10001:人太多了，请重试（sub_code: isv.business-failed:-10001） | 请稍后重试 |
| `50002` | 业务处理失败 / 10000002:未知错误（sub_code: isv.business-failed:10000002） | 请稍后重试 |
| `50002` | 业务处理失败 / 存在多个门店具有相同的门店 code，无法唯一确定唯一的门店 id（sub_code: isv.business-failed:-40013） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 当前品不能直接设置库存，因为他由其他品提供库存，请设置他背后的供货品库存（sub_code: isv.business-failed:-20048） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 门店 code 查不到门店信息（sub_code: isv.business-failed:-40014） | 请检查参数后重试 |
| `50002` | 业务处理失败 / -20047:仓必须先设置覆盖范围，才能增加库存, warehouse_id = 7408530027257839887, product_id = 3716281933467091238, sku_id = 3425519934124290,  本次操作号(logid) = 202411161131046FB1E10781D04C4C18BB（sub_code: isv.business-failed:-20047） | -20047:仓必须先设置覆盖范围，才能增加库存, warehouse_id = 7408530027257839887, product_id = 3716281933467091238, sku_id = 3425519934124290,  本次操作号(logid) = 202411161131046FB1E10781D04C4C18BB |
| `50002` | 业务处理失败 / -10005:Redis操作失败（sub_code: isv.business-failed:-10005） | -10005:Redis操作失败 |
| `50002` | 业务处理失败 / -20009:商品：3617345053376259848 （默认）正在参加平台活动（抖音商城冬日市集活动-官方立减&一件直降商品报名 ），无法修改库存信息（sub_code: isv.business-failed:-20009） | -20009:商品：3617345053376259848 （默认）正在参加平台活动（抖音商城冬日市集活动-官方立减&一件直降商品报名 ），无法修改库存信息 |
| `50002` | 业务处理失败 / -1000:设置主商品0库存，必须要传入storeid，用于确定门店子商品（sub_code: isv.business-failed:-1000） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 12000082:访问频率过高（sub_code: isv.business-failed:12000082） | 请降低访问频率 |
| `50002` | 业务处理失败 / 内部请求错误（sub_code: isv.business-failed:12000113） | 请稍后重试 |
| `50002` | 业务处理失败 / -24001:sku对应的仓库太多了（sub_code: isv.business-failed:-24001） | 请检查参数后重试 |
| `50002` | 业务处理失败 / -10011:仓库不存在（sub_code: isv.business-failed:-10011） | 请检查参数后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "results": [
      {
        "change_num": "1",
        "sku_id": "1751540901742600",
        "status_code": "0",
        "status_message": "-",
        "step_change_num": "2",
        "step_stock_num": "2",
        "stock_num": "1",
        "uniq_id": "uniqId1",
        "warehouse_id": "7155357637939495204"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:-30001",
  "sub_msg": "参数校验失败（check not pass）"
}
```

## 备注
