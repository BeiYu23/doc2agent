# sku.syncStockBatch

> 库存批量同步接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.sku.syncStockBatch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/syncStockBatch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/298 |
| 更新日期 | `2025-02-17` |

## 接口说明

- 文档书: 库存API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID，整型格式 | `3337589750809921129` |
| `idempotent_id` | body | string | 否 | 幂等ID，仅incremental=true时有用 | `2` |
| `incremental` | body | boolean | 是 | true表示增量库存，false表示全量库存，默认为false | `true` |
| `sku_sync_list` | body | array | 是 | 需要批量提交的skuid及对应的库存和仓；接口规则全部成功或全部失败，例：批量更新10个skuid库存，其中一个skuid信息不正确，这样整个请求都会失败，10个skuid都未更新成功。 | `` |
| `  └ batch_stock_items` | body | array | 否 | 批次库存项 | `` |
| `    └ batch_type` | body | mixed | 否 | 批次库存类型：1为唯一码 | `1` |
| `    └ stock_num` | body | mixed | 否 | 批次库存数量 | `1` |
| `    └ unique_id` | body | string | 否 | 唯一码 | `"356303487400309"` |
| `  └ multi_time_stocks` | body | array | 否 | 时效库存 | `` |
| `    └ stock_num` | body | mixed | 否 | 库存数 | `500` |
| `    └ time_desc` | body | string | 否 | 时效描述 | `5天内发` |
| `    └ time_type` | body | mixed | 否 | 时效 | `5` |
| `  └ outer_sku_id` | body | string | 否 | 外部sku编码，需要结合outer_product_id进行使用 | `232331` |
| `  └ sku_id` | body | mixed | 是 | skuid | `99758050` |
| `  └ sku_type` | body | mixed | 是 | 库存类型：0普通库存，1区域库存,10阶梯库存。 超市小时达子品传区域库存 | `1` |
| `  └ stock_num` | body | mixed | 否 | 普通库存数量 | `10` |
| `  └ step_stock_num` | body | mixed | 否 | 阶梯库存数量 | `10` |
| `  └ stock_map` | body | array | 否 | 区域库存配置 | `` |
| `    └ batch_stock_items` | body | array | 否 | 批次库存项 | `` |
| `      └ batch_type` | body | mixed | 否 | 批次库存类型：1为唯一码 | `1` |
| `      └ stock_num` | body | mixed | 否 | 批次库存数量 | `1` |
| `      └ unique_id` | body | string | 否 | 唯一码 | `"356303487400309"` |
| `    └ out_warehouse_id` | body | string | 是 | 仓id或到店自提门店id，场景①仓id，超市小时达子品传storeId。到店自提传入store_id（门店id） | `123` |
| `    └ stock_num` | body | mixed | 是 | 库存数量 | `10` |
| `  └ supplier_id` | body | string | 否 | 供应商ID | `1` |
| `outer_product_id` | body | string | 否 | 推荐使用，外部商家编码，支持字符串。 | `232334` |
| `store_id` | body | string | 否 | 即时零售连锁版，通过传入主品id+门店id对该门店下的子品进行操作，即时零售单店版，无需使用 | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/syncStockBatch?app_key=your_appkey_here&method=sku.syncStockBatch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 商品封禁，不可更新（sub_code: isv.business-failed:2010043） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商户状态不合法: 停业整顿状态（sub_code: isv.business-failed:2010005） | 请检查参数后重试 |
| `40004` | 非法的参数 / 更新库存数失败: 幂等ID重复（sub_code: isv.parameter-invalid:2010021） | 请勿重复请求 |
| `40004` | 非法的参数 / 查询商品信息失败，请检查参数后重试（sub_code: isv.parameter-invalid:2010013） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品已删除，不可更新（sub_code: isv.business-failed:2010042） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 商品审核中，不可更新（sub_code: isv.business-failed:2010041） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 更新库存数失败: 库存不足（sub_code: isv.business-failed:2010012） | 请检查参数后重试 |
| `40002` | 缺少必选参数 / 参数缺失（sub_code: isv.missing-parameter:2010004） | 请检查参数后重试 |
| `20000` | 系统错误 / 操作超时，请重试（sub_code: isp.service-error:2010002） | 请稍后重试 |
| `50002` | 业务处理失败 / 商品不存在或已彻底删除（sub_code: isv.business-failed:2010058） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后再试（sub_code: isv.business-failed:2010401） | 请稍后重试 |
| `20000` | 系统错误 / 内部请求错误（sub_code: isp.service-error:2010001） | 请稍后重试 |
| `50002` | 业务处理失败 / 商品正在参加平台活动，无法修改库存类型（sub_code: isv.business-failed:2010045） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 由于该商品基础分25（不达标），不支持快捷编辑价格/总库存，请点击右侧“编辑”进入商品详情页进行操作提醒：建议PC后台-商品优化-筛选“基础分不达标”，查看店铺所有不达标商品进行集中优化（sub_code: isv.business-failed:2010330） | 由于该商品基础分25（不达标），不支持快捷编辑价格/总库存，请点击右侧“编辑”进入商品详情页进行操作提醒：建议PC后台-商品优化-筛选“基础分不达标”，查看店铺所有不达标商品进行集中优化 |
| `50002` | 业务处理失败 / 商品正在参加平台活动（电视预售），不允许切换库存类型（sub_code: isv.business-failed:2010307） | 商品正在参加平台活动（电视预售），不允许切换库存类型 |
| `50002` | 业务处理失败 / 获取子商品信息失败（sub_code: isv.business-failed:7） | 获取子商品信息失败 |
| `50002` | 业务处理失败 / 奖品不支持设置区域库存（sub_code: isv.business-failed:110240124） | 奖品不支持设置区域库存 |
| `50002` | 业务处理失败 / 小时达子品必须为区域库存类型（sub_code: isv.business-failed:110240123） | 小时达子品必须为区域库存类型 |
| `50002` | 业务处理失败 / 学浪同步商品仅支持在学浪老师端编辑（sub_code: isv.business-failed:110102132） | 学浪同步商品仅支持在学浪老师端编辑 |

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
  "sub_code": "isv.business-failed:2010043",
  "sub_msg": "商品封禁，不可更新"
}
```

## 备注
