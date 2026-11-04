# 重新分配店铺主品对应的门店子品 (异步执行

> superm.product.batchRedistributeStoreProduct — 重新分配店铺主品对应的门店子品 (异步执行)

| 元信息 | 值 |
| --- | --- |
| 中文名 | 重新分配店铺主品对应的门店子品 (异步执行 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-product-batchRedistributeStoreProduct` |
| 接口 ID | `doudian.retail-store.superm.product.batchRedistributeStoreProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/batchRedistributeStoreProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2697 |
| 更新日期 | `2024-12-19` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_params` | body | object | 是 | 重新分配任务参数 | `` |
| `  └ start_sale_type` | body | mixed | 否 | 子品开售状态：0-立即上架售卖（默认）， 1-放入仓库，只对于新增子品有效 | `0` |
| `  └ main_product_id` | body | mixed | 是 | 店铺主商品ID | `3576410646054571500` |
| `  └ add_store_ids` | body | array | 否 | 需要铺品的门店ID列表 | `56386074,56386075` |
| `  └ del_store_ids` | body | array | 否 | 需要删除子品的门店ID列表 | `56386076,56386077` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.product.batchRedistributeStoreProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `root_task_id` | mixed | 异步任务根任务ID | `7158439918014824735` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010004:主商品信息不合法（sub_code: isv.business-failed:2010004） | 2010004:主商品信息不合法 |
| `50002` | 业务处理失败 / 2010001:提交异步任务出错（sub_code: isv.business-failed:2010001） | 2010001:提交异步任务出错 |

## 响应示例

成功：

```json
{
  "data": {
    "root_task_id": "7158439918014824735"
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
  "sub_code": "isv.business-failed:2010004",
  "sub_msg": "2010004:主商品信息不合法"
}
```

## 备注
