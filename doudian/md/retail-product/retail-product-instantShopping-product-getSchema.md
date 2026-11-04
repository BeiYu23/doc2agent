# 商品发布schema-渲染

> instantShopping.product.getSchema — 商品发布schema-渲染接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品发布schema-渲染 |
| 文档地址 | `/docs/doudian/retail-product/retail-product-instantShopping-product-getSchema` |
| 接口 ID | `doudian.retail-product.instantShopping.product.getSchema` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1570/7458 |
| 更新日期 | `2025-05-14` |

## 接口说明

- 文档书: 商品管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 否 | 类目Id | `31860` |
| `product_id` | body | mixed | 否 | 商品Id | `1232` |
| `spu_id` | body | mixed | 否 | SPU id | `1232` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.product.getSchema&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `model` | string | schem数据、json格式 | `{}` |
| `product_data` | object | 商品数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010001:获取店铺标签失败（sub_code: isv.business-failed:2010001） | 重试 |
| `50002` | 业务处理失败 / 2010004:类目ID必传（sub_code: isv.business-failed:2010004） | 2010004:类目ID必传 |
| `50002` | 业务处理失败 / 110105006:不支持操作奖品商品，请前往电脑端进行管理（sub_code: isv.business-failed:110105006） | 110105006:不支持操作奖品商品，请前往电脑端进行管理 |
| `50002` | 业务处理失败 / 110105001:不支持操作质检信息相关商品，请前往电脑端进行管理（sub_code: isv.business-failed:110105001） | 110105001:不支持操作质检信息相关商品，请前往电脑端进行管理 |
| `50002` | 业务处理失败 / 110201001:未查询到该类目（sub_code: isv.business-failed:110201001） | 110201001:未查询到该类目 |

## 响应示例

成功：

```json
{
  "data": {
    "model": "{}",
    "product_data": {
      "check_status": "3",
      "draft_status": "0",
      "status": "3"
    }
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
  "sub_code": "isv.business-failed:2010001",
  "sub_msg": "2010001:获取店铺标签失败"
}
```

## 备注
