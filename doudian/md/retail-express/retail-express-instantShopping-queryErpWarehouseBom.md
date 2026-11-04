# instantShopping.queryErpWarehouseBom

> erp服务商

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-express.instantShopping.queryErpWarehouseBom` |
| 中文名 | erp服务商 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1584/7521 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 合作快递【即时零售】（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `org_shop_id` | body | string | 是 | 抖音店铺ID | `123` |
| `request_time` | body | string | 是 | 关系修改的时间字段(使用业务动作发生时候的时间戳即可)，抖音侧基于时间字段会进行接口幂等的操作； 幂等逻辑 sku_id+request_time 同一个sku_id只有request_time更大的场景才会更新关系 | `1750240270` |
| `erp_sku_info_list` | body | array | 否 | erp货品列表 | `` |
| `  └ product_id` | body | string | 否 | 抖音侧商品id | `1750240270` |
| `  └ sku_id` | body | string | 否 | 抖音侧skuid | `1750240270` |
| `  └ bom_relation_info_list` | body | array | 否 | erp货品列表 | `` |
| `    └ warehouse_service_provider_id` | body | string | 否 | 仓服务商身份标,与ERP通过固定代码的方式约定得仓服务商的身份标志 | `11` |
| `    └ goods_num` | body | mixed | 否 | 货品数量 | `1` |
| `    └ warehouse_goods_id` | body | string | 否 | 仓服务商侧货品id | `1` |
| `    └ warehouse_owner_code` | body | string | 否 | 仓服务商的货主编码。 | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.queryErpWarehouseBom&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:40004） | 业务处理失败 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50040） | 业务处理失败 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:40001） | 业务处理失败 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:51040） | 业务处理失败 |

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
  "sub_code": "isv.business-failed:40004",
  "sub_msg": "业务处理失败"
}
```

## 备注
