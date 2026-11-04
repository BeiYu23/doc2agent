# 根据店铺主商品ID查询已经铺品的门店及子商品

> superm.product.getDistributedStoreProduct — 根据店铺主商品ID查询已经铺品的门店及子商品

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据店铺主商品ID查询已经铺品的门店及子商品 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-product-getDistributedStoreProduct` |
| 接口 ID | `doudian.retail-store.superm.product.getDistributedStoreProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/getDistributedStoreProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2693 |
| 更新日期 | `2022-11-02` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | number | 是 | 店铺主商品ID | `3576410646054571500` |
| `store_ids` | body | array | 否 | 门店列表 | `56386074,64145175` |
| `page` | body | number | 是 | 起始页 (从0开始) | `0` |
| `size` | body | number | 是 | 每页尺寸 (最大值50) | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/qualification/settle?app_key=your_appkey_here&method=qualification.settle&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_products` | array | 门店列表信息 | `` |
| `page` | number | 起始页 (从0开始) | `0` |
| `size` | number | 每页尺寸 (最大值50) | `10` |
| `total` | number | 商品总数 | `30` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010004:主商品信息不合法（sub_code: isv.business-failed:2010004） | 2010004:主商品信息不合法 |
| `50002` | 业务处理失败 / 2010001:查询渠道品信息失败（sub_code: isv.business-failed:2010001） | 2010001:查询渠道品信息失败 |

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
  "sub_code": "isv.business-failed:2010004",
  "sub_msg": "2010004:主商品信息不合法"
}
```

## 备注
