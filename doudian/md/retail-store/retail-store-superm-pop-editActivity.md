# 编辑小时达活动

> superm.pop.editActivity — 编辑小时达活动

| 元信息 | 值 |
| --- | --- |
| 中文名 | 编辑小时达活动 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-pop-editActivity` |
| 接口 ID | `doudian.retail-store.superm.pop.editActivity` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/pop/editActivity` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2969 |
| 更新日期 | `2023-02-17` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sd_activity_id` | body | string | 是 | 商达活动id | `745279695746453` |
| `main_skus` | body | array | 是 | 主商品sku信息列表 | `` |
| `  └ sku_id` | body | string | 是 | 主品skuid | `43524642` |
| `  └ product_id` | body | string | 是 | 主品id | `24385468594` |
| `  └ sub_skus` | body | array | 是 | 子商品sku信息列表 | `` |
| `    └ sku_id` | body | string | 是 | 子品skuid | `4265364643` |
| `    └ user_limit` | body | number | 否 | 每人限购 | `5` |
| `    └ product_id` | body | string | 是 | 子品id | `453896与5863` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/pop/editActivity?app_key=your_appkey_here&method=superm.pop.editActivity&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sd_activity_id` | string | 商达活动id | `745279695746453` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 操作不合法（sub_code: isv.parameter-invalid:50100） | 操作不合法 |
| `50002` | 业务处理失败 / 数据访问异常（sub_code: isv.business-failed:20100） | 数据访问异常 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:20201） | 系统异常 |
| `50002` | 业务处理失败 / 活动不存在（sub_code: isv.business-failed:20121） | 活动不存在 |
| `50002` | 业务处理失败 / 活动校验不通过（sub_code: isv.business-failed:20122） | 活动校验不通过 |
| `50002` | 业务处理失败 / 活动创建/更新失败（sub_code: isv.business-failed:20123） | 活动创建/更新失败 |
| `50002` | 业务处理失败 / 商品不存在（sub_code: isv.business-failed:20124） | 商品不存在 |
| `50002` | 业务处理失败 / 查询店铺信息异常（sub_code: isv.business-failed:20125） | 查询店铺信息异常 |
| `50002` | 业务处理失败 / 查询门店信息异常（sub_code: isv.business-failed:20126） | 查询门店信息异常 |
| `50002` | 业务处理失败 / 商品中心/商品服务错误（sub_code: isv.business-failed:20221） | 商品中心/商品服务错误 |
| `50002` | 业务处理失败 / 商达营销服务错误（sub_code: isv.business-failed:20222） | 商达营销服务错误 |
| `50002` | 业务处理失败 / 库存中心服务错误（sub_code: isv.business-failed:20223） | 库存中心服务错误 |
| `50002` | 业务处理失败 / 营销中心服务错误（sub_code: isv.business-failed:20224） | 营销中心服务错误 |
| `50002` | 业务处理失败 / 商品中心/商品服务错误（sub_code: isv.business-failed:20225） | 商品中心/商品服务错误 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |

## 响应示例

成功：

```json
{
  "data": {
    "sd_activity_id": "745279695746453"
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
  "sub_code": "isv.parameter-invalid:50100",
  "sub_msg": "操作不合法"
}
```

## 备注
