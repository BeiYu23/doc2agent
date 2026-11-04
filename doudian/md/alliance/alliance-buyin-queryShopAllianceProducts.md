# 联盟商家-查询店铺联盟推广

> buyin.queryShopAllianceProducts — 联盟商家-查询店铺联盟推广

| 元信息 | 值 |
| --- | --- |
| 中文名 | 联盟商家-查询店铺联盟推广 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-queryShopAllianceProducts` |
| 接口 ID | `doudian.alliance.buyin.queryShopAllianceProducts` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/queryShopAllianceProducts` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2408 |
| 更新日期 | `2023-12-14` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 分页页数，从1开始 | `1` |
| `size` | body | mixed | 是 | 分页大小，最大20 | `20` |
| `product_ids` | body | array | 否 | 商品ID列表，用“,”分隔 | `35632345453243,34242532432` |
| `status` | body | mixed | 否 | 商品状态。2：商品在架；3：商家关闭推广；4：商品下架；6：平台治理关闭；99：商家删除 | `2` |
| `title` | body | string | 否 | 商品名称 | `测试商品的名称` |
| `in_stock` | body | boolean | 否 | 是否有库存 | `true` |
| `check_status` | body | array | 否 | 审核状态。 0：未审核；2：审核未通过；3：审核通过 | `3` |
| `sort_by` | body | string | 否 | 排序字段。 update_time: 更新时间; cos_ratio: 佣金率 | `update_time` |
| `sort_order` | body | string | 否 | 排序方式（Desc或者Asc）。Desc：降序；Asc：生序 | `Desc` |
| `fields` | body | array | 否 | 加载更多的字段，如 is_exclusive | `["is_exclusive"]` |
| `launch` | body | mixed | 否 | 0或者不填：原联盟计划商品 1：查询新投放商品 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/queryShopAllianceProducts?app_key=your_appkey_here&method=buyin.queryShopAllianceProducts&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数，最大10000 | `200` |
| `product_list` | array | 商品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 无效分页大小 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "product_list": [
      {
        "check_status": "3",
        "cos_fee": "50",
        "cos_ratio": "50.00",
        "cover": "https://sf1-ttcdn-tos.pstatp.com/img/temai/Fpt8fam5_q50.webp",
        "create_time": "1650007266",
        "detail_url": "https://haohuo.jinritemai.com/views/product/item2?id=34312324232145",
        "imgs": "[\"https://p3-aio.ecombdimg.com/obj/temai/5f2e085982cbad84cadb30a100d42a09ww\"]",
        "is_exclusive": "false",
        "market_price": "100",
        "price": "100",
        "product_id": "34312324232145",
        "sales": "0",
        "sample_conf": {
          "buy_style": "1",
          "buy_volume_limit": "5"
        },
        "status": "2",
        "title": "测试商品的名称",
        "update_time": "1660790303"
      }
    ],
    "total": "200"
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
  "sub_code": "isv.parameter-invalid:1031",
  "sub_msg": "无效size"
}
```

## 备注
