# supplyChain.supplyProduct.getSupplyProductList

> 获取供销产品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.getSupplyProductList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2549 |
| 更新日期 | `2026-08-05` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | mixed | 否 | 主状态值 | `1` |
| `sub_status` | body | mixed | 否 | 子状态值 | `1` |
| `create_start_time` | body | mixed | 否 | 创建开始时间 | `1657800575` |
| `create_end_time` | body | mixed | 否 | 创建结束时间 | `1657800575` |
| `page` | body | mixed | 否 | 页码，第一页从1开始 | `1` |
| `size` | body | mixed | 否 | 每页大小， 不传或超过50会默认设置为50 | `50` |
| `update_start_time` | body | mixed | 否 | 更新开始时间 | `1657800575` |
| `update_end_time` | body | mixed | 否 | 更新结束时间 | `1657800575` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProduct.getSupplyProductList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回值 | `` |
| `page` | mixed | 当前页数 | `1` |
| `size` | mixed | 每页大小 | `50` |
| `total` | mixed | 总页数 | `3` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 3200:创建分销品错误（sub_code: isv.business-failed:3200） | 3200:创建分销品错误 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_detail": {
          "first_cid": "11111111",
          "first_cname": "一级类目名称",
          "fourth_cid": "111111",
          "fourth_cname": "四级类目名称",
          "second_cid": "1111111",
          "second_cname": "二级类目名称",
          "third_cid": "11111",
          "third_cname": "三级类目名称"
        },
        "create_time": "1657800575",
        "distribution_status": "distributable",
        "img": "\\\"https://sf6-ttcdn-tos.pstatp.com/obj/temai/0c71ce6acb4e3b508e0d30042b1a94262818ab41www800-800\\\"",
        "name": "测试名称",
        "non_distributable_reason": "因货品信息缺失，该货品已在抖店已不可被分销，请尽快完成货品信息的补充，补充后货品将在次日于\"抖店-精选货源\"中恢复展示。",
        "original_category_detail": {
          "first_cid": "111111",
          "first_cname": "一级类目名称",
          "fourth_cid": "44444",
          "fourth_cname": "四级类目名称",
          "second_cid": "22222",
          "second_cname": "二级类目名称",
          "third_cid": "33333",
          "third_cname": "三级类目名称"
        },
        "outer_product_id": "11111111",
        "product_id": "111111111",
        "standard_brand_id": "13123123",
        "status": "1",
        "sub_status": "1",
        "update_time": "1657800575",
        "zhili_reject_reasons": "[\"分销品标题未明确描述分销品品名，请重新填写。\"]"
      }
    ],
    "page": "1",
    "size": "50",
    "total": "3"
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
  "sub_code": "isv.business-failed:3200",
  "sub_msg": "3200:创建分销品错误"
}
```

## 备注
