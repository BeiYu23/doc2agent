# yunc.erpCargoSinglePush

> 货品推送接口-ERP(单个)

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.erpCargoSinglePush` |
| 中文名 | 货品推送接口-ERP(单个 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/erpCargoSinglePush` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/932 |
| 更新日期 | `2025-11-28` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id` | body | mixed | 是 | 抖店店铺id | `1001` |
| `cargo_name` | body | string | 是 | 货品名称 | `iphone6s` |
| `cargo_desc` | body | string | 否 | 货品描述 | `这是一段描述` |
| `english_name` | body | string | 否 | 货品英文名 | `iphone6s` |
| `stock_unit` | body | string | 否 | 计量单位, 枚举值: 台, 双, 本, 支, 片, 个, 套, 件, 副, 束, 盒 | `件` |
| `length_unit` | body | string | 否 | 长度单位, 枚举值: mm, cm, m, km. 最小精度为整数位mm | `厘米` |
| `length` | body | string | 否 | 长 | `10.01` |
| `width` | body | string | 否 | 宽 | `10.01` |
| `height` | body | string | 否 | 高 | `10.01` |
| `weight_unit` | body | string | 否 | 重量单位, 枚举值: g, kg. 默认为g. 最小精度为整数位g | `千克` |
| `gross_weight` | body | string | 否 | 毛重 | `10.01` |
| `net_weight` | body | string | 否 | 净重 | `10.01` |
| `currency_unit` | body | string | 否 | 货币单位, 枚举值: USD, CNY, EUR, GBP | `元` |
| `market_price` | body | string | 否 | 市场价(吊牌价) | `10.01` |
| `supply_price` | body | string | 否 | 采购价 | `10.01` |
| `retail_price` | body | string | 否 | 零售价 | `10.01` |
| `is_embargo` | body | mixed | 否 | 是否航空禁运品；0否1是 | `1` |
| `is_fragile` | body | mixed | 否 | 是否易碎品；0否1是 | `1` |
| `is_large` | body | mixed | 否 | 是否大件；0否1是 | `1` |
| `is_precious` | body | mixed | 否 | 是否贵重品；0否1是 | `1` |
| `is_need_valid` | body | mixed | 否 | 是否效期管理；0否1是 | `1` |
| `is_liquid` | body | mixed | 否 | 是否液体 | `1` |
| `is_hazardous` | body | mixed | 否 | 是否危险品 | `1` |
| `period_of_validity` | body | mixed | 否 | 有效期；以天为单位 | `90` |
| `period_of_forbid_sale` | body | mixed | 否 | 禁售期；以天为单位. 按有效期计算, 计算规则以平台为准 | `90` |
| `period_of_forbid_take` | body | mixed | 否 | 禁收期；以天为单位. 按有效期计算, 计算规则以平台为准 | `90` |
| `period_of_warning` | body | mixed | 否 | 临期预警天数；以天为单位 | `90` |
| `is_need_batch` | body | mixed | 否 | 是否批次管理；0否1是 | `1` |
| `batch_type` | body | mixed | 否 | 批次类型（1：生产批次/2：采购批次/3：收货批次） | `1` |
| `is_must_batch` | body | mixed | 否 | 是否强批次管理；0否1是 | `1` |
| `accessory_info` | body | string | 否 | 配件信息，字符串展示, 如"电源 * 1, 数据线 * 2" | `电源 * 1, 数据线 * 2` |
| `origin_address` | body | string | 否 | 产地，一般给国家-省两级信息即可 | `中国浙江省` |
| `tax_rate` | body | string | 否 | 增值税率 | `10%` |
| `delivery_temp` | body | string | 否 | 运输温度 | `32.5` |
| `storage_temp` | body | string | 否 | 存储温度 | `32.5` |
| `brand_code` | body | string | 否 | 品牌编码 | `1001` |
| `brand_name` | body | string | 否 | 品牌名称 | `苹果` |
| `picture` | body | string | 否 | 货品图片 | `http://alicdn.xx.com/1.jgp` |
| `erp_sku_id` | body | string | 是 | 商家ERP的sku_id | `x01` |
| `category_id` | body | mixed | 否 | 叶子类目id | `1001` |
| `category_name` | body | string | 否 | 叶子类目名称 | `电脑` |
| `barcode` | body | array | 是 | 条形码 | `123` |
| `props_extends` | body | array | 否 | 货品扩展描述属性 | `` |
| `  └ prop_val_id` | body | mixed | 否 | 属性值id | `1001` |
| `  └ prop_key_id` | body | mixed | 否 | 属性keyId | `1001` |
| `  └ prop_key` | body | string | 否 | 属性key | `材质` |
| `  └ prop_val` | body | string | 否 | 属性值 | `木板` |
| `sku_props` | body | array | 否 | 货品销售规格 | `` |
| `  └ prop_key_id` | body | mixed | 否 | 销售规格keyId | `101` |
| `  └ prop_val` | body | string | 否 | 销售规格值 | `白色` |
| `  └ prop_key` | body | string | 否 | 销售规格名称 | `颜色` |
| `  └ prop_val_id` | body | mixed | 否 | 销售规格值id | `101` |
| `category_detail` | body | object | 否 | 类目详情 | `` |
| `  └ third_cid` | body | mixed | 否 | 三级类目id | `111` |
| `  └ first_cname` | body | string | 否 | 一级类目名称 | `数码/3c` |
| `  └ fourth_cname` | body | string | 否 | 四级类目名称 | `苹果手机` |
| `  └ second_cid` | body | mixed | 否 | 二级类目id | `11` |
| `  └ first_cid` | body | mixed | 否 | 一级类目id | `1` |
| `  └ third_cname` | body | string | 否 | 三级类目名称 | `智能手机` |
| `  └ second_cname` | body | string | 否 | 二级类目名称 | `手持设备` |
| `  └ fourth_cid` | body | mixed | 否 | 四级类目id | `1111` |
| `status` | body | mixed | 是 | 货品状态：1正常 -1停用 | `1` |
| `warehouse_code` | body | string | 是 | 仓库编码，2023.6.26日后，请默认传空串，平台会全自动推品到订购的所有仓，无需制定具体某一个仓了 | `""` |
| `relation_list` | body | array | 否 | 商货关系列表 | `` |
| `  └ erp_sku_id` | body | string | 否 | ERP侧skuID | `ABCD` |
| `  └ package_erp_sku_list` | body | array | 否 | 组合品sku列表，is_package_erp_sku为0，则无本结构 | `` |
| `    └ sub_erp_sku_list` | body | array | 否 | 组套关系 | `` |
| `      └ spec_id_list` | body | array | 否 | 抖店商品SKU | `` |
| `        └ shop_id` | body | mixed | 否 | 抖店店铺id | `123456` |
| `        └ spec_id` | body | string | 否 | 抖店商品SKUID | `14213294743` |
| `        └ product_id` | body | string | 否 | 抖音侧商品Id | `62313294743` |
| `      └ quantity` | body | mixed | 否 | 数量 | `5` |
| `      └ erp_sku_id` | body | string | 否 | 对应ERP子品SKUID | `24186443` |
| `    └ package_sku_id` | body | string | 否 | 抖音组合商品Id | `24186443` |
| `    └ shop_id` | body | mixed | 否 | 抖店店铺id | `123456` |
| `    └ package_erp_sku_id` | body | string | 否 | ERP组合商品ID | `24186443` |
| `    └ product_id` | body | string | 否 | 抖音侧商品Id | `62313294743` |
| `  └ cargo_code` | body | string | 否 | 货品编码 | `7643824637246` |
| `  └ spec_id_list` | body | array | 否 | 对应抖店商品SKUID, 货品SKUID是否属于组合品为0时，此结构体才有值 | `` |
| `    └ product_id` | body | string | 否 | 抖音侧商品Id | `62313294743` |
| `    └ spec_id` | body | string | 否 | 抖店商品SKUID | `14213294743` |
| `    └ shop_id` | body | mixed | 否 | 抖店店铺id | `123456` |
| `  └ is_package_erp_sku` | body | mixed | 否 | 商品SKUID是否属于组合品： 0：单品（非组合品，也不从属组合品），1:组合品，2：从属某个组合品 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpCargoSinglePush?app_key=your_appkey_here&method=yunc.erpCargoSinglePush&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `erp_sku_id` | string | erp的sku_id | `1001` |
| `cargo_code` | string | 字节平台货品编码 | `X01` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务异常（sub_code: isp.service-error:1000） | 请稍后重试 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:3000） | 请根据报错修复参数 |
| `50002` | 业务处理失败 / 并发更新失败（sub_code: isv.business-failed:3202） | 请稍后重试 |
| `50002` | 业务处理失败 / 并发更新失败（sub_code: isv.business-failed:3201） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "cargo_code": "X01",
    "erp_sku_id": "1001"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000",
  "sub_msg": "服务异常"
}
```

## 备注
