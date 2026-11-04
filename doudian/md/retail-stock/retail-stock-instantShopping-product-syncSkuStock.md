# 全量/增量更新商品sku库存

> instantShopping.product.syncSkuStock — 全量/增量更新商品sku库存

| 元信息 | 值 |
| --- | --- |
| 中文名 | 全量/增量更新商品sku库存 |
| 文档地址 | `/docs/doudian/retail-stock/retail-stock-instantShopping-product-syncSkuStock` |
| 接口 ID | `doudian.retail-stock.instantShopping.product.syncSkuStock` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1594/7449 |
| 更新日期 | `2025-10-22` |

## 接口说明

- 文档书: 库存管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `code` | body | string | 否 | sku编码 | `dy001` |
| `sku_id` | body | mixed | 否 | 规格id；抖店系统生成，商品id下唯一。 | `1737398770243598` |
| `out_sku_id` | body | mixed | 否 | 外部skuid，开发者在创建或更新商品时设置。 | `44354354` |
| `product_id` | body | string | 否 | 商品ID，抖店系统生成，店铺下唯一；长度19位。 | `3539925204033339668` |
| `out_product_id` | body | mixed | 否 | 外部商品id；开发者在创建或更新商品时设置的。 | `435243654356` |
| `out_warehouse_id` | body | string | 否 | 外部仓库id编码，开发者自定义；如传入传值表示更新区域库存，不传默认更新普通库存。可以使用【/warehouse/list】接口响应参数【out_warehouse_id】字段获取。超市小时达店铺类型，需传入store_id字段，store_id可以使用【/shop/batchCreateStore】创建成功后获取 | `dy123` |
| `supplier_id` | body | string | 否 | 供应商ID | `1` |
| `incremental` | body | boolean | 否 | 库存更新方式；true-增量更新，同时idempotent_id字段必填；false-全量更新；默认为false | `false` |
| `idempotent_id` | body | string | 否 | 幂等ID，当incremental=true时该参数必传 | `202206021500001001` |
| `stock_num` | body | mixed | 是 | 库存值；可以设置为0，不能小于0，当incremental=true时stock_num支持加/减库存。支持传入“-”，例如：-5表示减5个库存；加库存例：原商品库存是10个，接口传入5个，执行成功商品库存是15个。减库存例：原商品库存是10个，接口stock_num传入-5，执行成功商品库存是5个。注意：减库存时【商品现库存-即将减少库存数不能<0】，否则会报错系统错误:更新库存数失败: 库存不足； | `100` |
| `step_stock_num` | body | mixed | 否 | 阶梯库存 | `100` |
| `store_id` | body | string | 否 | 门店id①即时零售连锁版，通过传入主品id+门店id对该门店下的子品进行操作，即时零售单店版，无需使用②抖店服饰自提场景，通过传入主品id+门店id更新门店商品库存 | `12345` |
| `multi_time_stocks` | body | array | 否 | 时效库存 | `` |
| `  └ stock_num` | body | mixed | 否 | 库存数 | `500` |
| `  └ time_desc` | body | string | 否 | 时效描述 | `5天内发` |
| `  └ time_type` | body | mixed | 否 | 时效 | `5` |
| `batch_stock_items` | body | array | 否 | 批次库存项 | `` |
| `  └ batch_type` | body | mixed | 否 | 批次库存类型：1为唯一码 | `1` |
| `  └ stock_num` | body | mixed | 否 | 批次库存数量 | `1` |
| `  └ unique_id` | body | string | 否 | 唯一码 | `"356303487400309"` |
| `inventory_loss` | body | boolean | 否 | 供应链盘亏强扣，true表示允许库存传负值 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.product.syncSkuStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 当前sku已被删除,禁止修改库存（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010401:系统繁忙，请稍后再试（sub_code: isv.business-failed:2010401） | 2010401:系统繁忙，请稍后再试 |
| `40004` | 非法的参数 / sku_id: 21062210000363, 找不到对应的sku（sub_code: isv.parameter-invalid:5） | 请检查请求参数的skuid是否存在或商品已经被删除 |
| `40004` | 非法的参数 / [idempotent_id]重复，操作已执行（sub_code: isv.parameter-invalid:40010） | idempotent_id需要保持唯一性，请检查替换idempotent_id值 |
| `40004` | 非法的参数 / 系统错误:获取区域仓失败（sub_code: isv.parameter-invalid:40004） | 此报错是超时导致，重试即可 |
| `50002` | 业务处理失败 / 获取子商品信息失败（sub_code: isv.business-failed:7） | 获取子商品信息失败 |
| `50002` | 业务处理失败 / 商品：3679752912201973760 （浅米杏-M）正在参加平台活动（抖音商城618好物节-官方立减&一件直降商品报名），无法修改库存信息（sub_code: isv.business-failed:2010012） | 商品：3679752912201973760 （浅米杏-M）正在参加平台活动（抖音商城618好物节-官方立减&一件直降商品报名），无法修改库存信息 |
| `50002` | 业务处理失败 / 查询商品信息失败，请检查参数后重试（sub_code: isv.business-failed:2010058） | 查询商品信息失败，请检查参数后重试 |
| `50002` | 业务处理失败 / 系统错误:Sku不存在（sub_code: isv.business-failed:2010001） | 系统错误:Sku不存在 |
| `50002` | 业务处理失败 / 商品已删除，不可更新（sub_code: isv.business-failed:2010042） | 商品已删除，不可更新 |
| `50002` | 业务处理失败 / 找不到对应的sku（sub_code: isv.business-failed:2010004） | 找不到对应的sku |
| `50002` | 业务处理失败 / 当前店铺已停业，重新开店后可支持创建商品（sub_code: isv.business-failed:2010005） | 当前店铺已停业，重新开店后可支持创建商品 |
| `50002` | 业务处理失败 / 商品封禁，不可更新（sub_code: isv.business-failed:2010043） | 商品封禁，不可更新 |
| `50002` | 业务处理失败 / 当前sku为区域库存，禁止更新为普通库存（当前接口禁止更新skuType）（sub_code: isv.business-failed:110240119） | 当前sku为区域库存，禁止更新为普通库存（当前接口禁止更新skuType） |
| `50002` | 业务处理失败 / 更新库存数失败（sub_code: isv.business-failed:110211009） | 更新库存数失败 |
| `50002` | 业务处理失败 / 当前sku为普通库存，禁止更新为区域库存（当前接口禁止更新skuType）（sub_code: isv.business-failed:110240120） | 当前sku为普通库存，禁止更新为区域库存（当前接口禁止更新skuType） |
| `50002` | 业务处理失败 / 商品正在参加平台活动（赠品活动），无法修改商品信息（sub_code: isv.business-failed:2010045） | 商品正在参加平台活动（赠品活动），无法修改商品信息 |
| `50002` | 业务处理失败 / 阶梯库存模式不合法（sub_code: isv.business-failed:2010341） | 阶梯库存模式不合法 |
| `50002` | 业务处理失败 / 商品审核中，不可更新（sub_code: isv.business-failed:2010041） | 商品审核中，不可更新 |
| `50002` | 业务处理失败 / 当前商品设置达人库存，不可修改库存类型（sub_code: isv.business-failed:110240107） | 当前商品设置达人库存，不可修改库存类型 |
| `50002` | 业务处理失败 / 跨境商品仅支持一品一仓，如需修改商品所在仓请使用编辑接口（sub_code: isv.business-failed:110240116） | 跨境商品仅支持一品一仓，如需修改商品所在仓请使用编辑接口 |
| `50002` | 业务处理失败 / 学浪同步商品仅支持在学浪老师端编辑（sub_code: isv.business-failed:110102132） | 学浪同步商品仅支持在学浪老师端编辑 |
| `50002` | 业务处理失败 / 获取库存数失败（sub_code: isv.business-failed:20100） | 获取库存数失败 |
| `50002` | 业务处理失败 / 读取商品失败（sub_code: isv.business-failed:20053） | 读取商品失败 |
| `50002` | 业务处理失败 / 系统异常，请稍后尝试（sub_code: isv.business-failed:20050） | 系统异常，请稍后尝试 |
| `50002` | 业务处理失败 / 110502038:有价券商品不支持当前接口操作（sub_code: isv.business-failed:110502038） | 110502038:有价券商品不支持当前接口操作 |
| `50002` | 业务处理失败 / 2010013:获取V2库存数失败（sub_code: isv.business-failed:2010013） | 2010013:获取V2库存数失败 |

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
  "sub_code": "isv.parameter-invalid:4",
  "sub_msg": "当前sku已被删除,禁止修改库存"
}
```

## 备注
