# alliance.colonelGetOfficialSelectionProductList

> 团长拉取爆品合伙人选品库商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.colonelGetOfficialSelectionProductList` |
| 中文名 | 团长拉取爆品合伙人选品库商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/colonelGetOfficialSelectionProductList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/8361 |
| 更新日期 | `2026-10-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `commission_rate` | body | string | 否 | - 佣金率筛选，可指定佣金范围，支持如下格式   - 0,5   - 10,20   - 20,30   - 30,40   - 40,50   - 50,-1 | `10` |
| `order_by` | body | string | 否 | asc:升序，desc:降序，默认desc | `desc` |
| `month_sales` | body | mixed | 否 | - 月销筛选，可筛选月销满足要求的商品，支持如下格式   - 1  含义是>=5千   - 2  含义是>=1万   - 3  含义是>=2万   - 4  含义是>=3万   - 5  含义是>=5万 | `-1` |
| `query_info` | body | string | 否 | 可指定商品信息/店铺信息查询 | `衣服` |
| `shop_score` | body | mixed | 否 | - 店铺分筛选，可筛选店铺分达标的商品，支持如下格式   - 1  含义是>=80分   - 2  含义是>=85分   - 3  含义是>=90分   - 4  含义是>=95分   - 5  含义是=100分 | `-1` |
| `cat_id` | body | mixed | 否 | 行业类目筛选，可指定电商行业大类id | `-1` |
| `order_field` | body | string | 否 | - 排序字段，支持如下四种排序   - product_price   - commission_rate   - month_sales   - promoters_count | `product_price` |
| `page` | body | mixed | 否 | 默认1 | `1` |
| `product_price` | body | string | 否 | - 商品价格筛选，可指定价格范围，支持如下格式   - 0,10   - 10,30   - 30,50   - 50,100   - 100,500   - 500,-1 | `-1` |
| `service_rate` | body | string | 否 | - 服务费率筛选，可指定服务费范围，支持如下格式   - 0,3   - 3,5   - 5,8   - 10,-1 | `-1` |
| `promote_time` | body | mixed | 否 | - 可合作时间筛选，可指定合作到期时间范围，支持如下格式   - 0  含义是>=7天   - 1  含义是>=30天   - 2  含义是>=90天   - 3  含义是>=180天   - 4  含义是>=360天 | `-1` |
| `promoters_count` | body | string | 否 | - 带货达人数筛选，可筛选商品的带货达人数量，支持如下格式   - 100 含义是>=100个达人   - 200 含义是>=200个达人   - 500 含义是>=500个达人   - 1000 含义是>=1000个达人 | `-1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/colonelGetOfficialSelectionProductList?app_key=your_appkey_here&method=alliance.colonelGetOfficialSelectionProductList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `has_more` | boolean | 是否有更多 | `true` |
| `base_resp` | object | 接触返回 | `` |
| `total` | mixed | 商品总数 | `100` |
| `product_list` | array | 商品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 110110:获取商品列表失败（sub_code: isv.business-failed:110110） | '' |

## 响应示例

成功：

```json
{
  "data": {
    "base_resp": {
      "status_code": "0",
      "status_message": "成功"
    },
    "has_more": "true",
    "product_list": [
      {
        "ad_commission_rate": "10",
        "ad_service_rate": "10",
        "alliance_month_sales": "1234",
        "channel_type_percent": "[15,85]",
        "commission_rate": "10",
        "common_ad_commission_rate": "10",
        "common_commission_rate": "10",
        "common_cos_type": "1",
        "cos_type": "1",
        "origin_activity_id": "1234",
        "origin_institution_id": "12345123512",
        "origin_institution_name": "团长A",
        "product_id": "13251235123",
        "product_img": "https://product.img",
        "product_name": "测试商品",
        "promoters_count": "123",
        "promotion_end_time": "2026/06/01",
        "promotion_end_time_desc": ">=30天",
        "service_rate": "10",
        "shop_id": "1234",
        "shop_name": "测试商家",
        "shop_score": "85",
        "views": "100"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.business-failed:110110",
  "sub_msg": "110110:获取商品列表失败"
}
```

## 备注
