# 检索精选联盟商品，需达人/抖客授权

> buyin.kolMaterialsProductsSearch — 检索精选联盟商品，需达人/抖客授权

| 元信息 | 值 |
| --- | --- |
| 中文名 | 检索精选联盟商品，需达人/抖客授权 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-kolMaterialsProductsSearch` |
| 接口 ID | `doudian.alliance.buyin.kolMaterialsProductsSearch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/kolMaterialsProductsSearch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1725 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `title` | body | string | 否 | 商品标题，返回标题中包含某个关键词的商品 | `测试商品名称` |
| `first_cids` | body | array | 否 | 筛选商品一级类目 | `[1,2,3,4]` |
| `second_cids` | body | array | 否 | 筛选商品二级类目 | `[22]` |
| `third_cids` | body | array | 否 | 筛选商品三级类目 | `[333]` |
| `price_min` | body | mixed | 否 | 筛选价格区间-最小值（单位为分） | `1` |
| `price_max` | body | mixed | 否 | 筛选价格区间-最大值（单位为分） | `1000` |
| `sell_num_min` | body | mixed | 否 | 筛选历史销量区间-最小值 | `0` |
| `sell_num_max` | body | mixed | 否 | 筛选历史销量区间-最大值 | `1000` |
| `search_type` | body | mixed | 是 | 召回结果排序条件，0默认排序1历史销量排序2价格排序3佣金金额排序4佣金比例排序； | `0` |
| `sort_type` | body | mixed | 是 | 排序顺序（0升序1降序） | `0` |
| `cos_fee_min` | body | mixed | 否 | 筛选普通佣金区间-最小值（单位为分） | `1` |
| `cos_fee_max` | body | mixed | 否 | 筛选普通佣金区间-最大值（单位为分） | `50` |
| `cos_ratio_min` | body | mixed | 否 | 筛选普通佣金率区间-最小值 （乘100，例如1.1%为110） | `1` |
| `cos_ratio_max` | body | mixed | 否 | 筛选普通佣金率区间-最大值（乘100，例如1.1%为110） | `15` |
| `page` | body | mixed | 是 | 分页（从1开始） | `1` |
| `page_size` | body | mixed | 是 | 每页的数量（小于等于20） | `10` |
| `share_status` | body | mixed | 否 | 获取商品分销状态。1: 仅返回可分销商品；0:返回全量商品 | `1` |
| `activity_id` | body | mixed | 否 | 【废弃】推荐使用tag字段。 | `1` |
| `tag` | body | mixed | 否 | 商品标签。 0:返回全量商品; 1:返回超值购商品; 2:返回抖音超市(次日达)商品 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolMaterialsProductsSearch?app_key=your_appkey_here&method=buyin.kolMaterialsProductsSearch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 商品总数 | `1000` |
| `products` | array | 商品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败: 无效搜索类型（sub_code: isv.parameter-invalid:4098） | 无效搜索类型 |
| `40004` | 非法的参数 / 参数校验失败: 无效分页大小（sub_code: isv.parameter-invalid:4097） | 无效分页大小 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 无效百应ID（sub_code: isv.business-failed:4173） | 请重新授权 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 今日访问商品数已达上限（sub_code: isv.business-failed:4195） | 今日访问商品数已达上限 |

## 响应示例

成功：

```json
{
  "data": {
    "products": [
      {
        "activity_id": "1",
        "available_coupons": [
          {
            "apply_end_time": "2016-01-01 13:00:00",
            "apply_start_time": "2016-01-01 12:00:00",
            "coupon_type": "1",
            "discount_desc": "满20减1",
            "type_desc": "平台券",
            "use_end_time": "2016-01-01 13:00:00",
            "use_start_time": "2016-01-01 12:00:00",
            "valid_period": "3600",
            "validity_type": "1"
          }
        ],
        "commission_type": "1",
        "cos_fee": "1",
        "cos_ratio": "10",
        "coupon_price": "92",
        "cover": "https://sf1-ttcdn-tos.pstatp.com/img/temai/Fpt8famR3twTGYz09e25nz5PbTRuwww800-800~1125x1125_q50.webp",
        "detail_url": "https://haohuo.jinritemai.com/views/product/item2?id=3400312511185213726",
        "first_cid": "1206",
        "in_stock": "1",
        "kol_ad_cos_fee": "10",
        "kol_ad_cos_ratio": "10.00",
        "kol_cos_fee": "10",
        "kol_cos_ratio": "10.00",
        "limit_min_sale": "false",
        "post_free": "true",
        "presell_type": "0",
        "price": "100",
        "product_id": "3400312511185213726",
        "sales": "1234",
        "second_cid": "1402",
        "sharable": "true",
        "shop_id": "2232",
        "shop_name": "maggie测试小铺",
        "third_cid": "2634",
        "title": "测试商品"
      }
    ],
    "total": "1000"
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
  "sub_code": "isv.parameter-invalid:4098",
  "sub_msg": "参数校验失败: 无效搜索类型"
}
```

## 备注
