# C端小程序获取门店列表

> mini.getStoreList — C端小程序获取门店列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | C端小程序获取门店列表 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-getStoreList` |
| 接口 ID | `doudian.miniapp.mini.getStoreList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/getStoreList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7260 |
| 更新日期 | `2025-02-21` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_size` | body | mixed | 是 | 每页大小 | `20` |
| `stock_param` | body | object | 否 | 库存参数 | `` |
| `  └ sku_list` | body | array | 否 | sku信息 | `` |
| `    └ sku_id` | body | mixed | 否 | SkuId | `123` |
| `    └ stock_num` | body | mixed | 否 | 购买的Sku数量 | `3` |
| `    └ sku_type` | body | mixed | 否 | sku库存类型，0普通库存，1区域库存 | `1` |
| `    └ promation_stock_type` | body | mixed | 否 | 是否使用活动库存，0：使用 1：不使用 | `0` |
| `    └ store_id` | body | mixed | 否 | 门店Id（可不传） | `/` |
| `    └ store_id_list` | body | array | 否 | 门店Id list | `[1234]` |
| `    └ delivery_mode` | body | mixed | 否 | -1 未指定 0 物流发货 1 自提 | `1` |
| `    └ product_id` | body | mixed | 否 | 商品ID | `12341234` |
| `    └ activity_id` | body | mixed | 否 | 活动id | `12341234` |
| `store_id_list` | body | array | 否 | 门店Id list | `/` |
| `delivery_mode` | body | mixed | 否 | -1 未指定 0 物流发货 1 自提 | `1` |
| `store_library_id` | body | string | 否 | 门店组Id | `1` |
| `lbs_info` | body | object | 否 | 起点经纬度 | `` |
| `  └ latitude` | body | string | 否 | 纬度 | `31.1` |
| `  └ longitude` | body | string | 否 | 经度 | `120.1` |
| `address` | body | object | 否 | 地址信息 | `` |
| `  └ city` | body | string | 否 | 市 | `上海市` |
| `  └ district` | body | string | 否 | 区 | `杨浦区` |
| `  └ province` | body | string | 否 | 省 | `上海市` |
| `  └ city_code` | body | string | 否 | 市代码 | `310000` |
| `  └ district_code` | body | string | 否 | 区代码 | `310110` |
| `  └ province_code` | body | string | 否 | 省代码 | `31` |
| `page` | body | mixed | 是 | 页码 | `0` |
| `store_library_ids` | body | array | 是 | 门店需要满足的所有门店组ID | `123415123123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/getStoreList?app_key=your_appkey_here&method=mini.getStoreList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 门店总数 | `3` |
| `page` | mixed | 页码 | `0` |
| `page_size` | mixed | 每页大小 | `20` |
| `store_list` | array | 门店列表 | `` |
| `custom_err` | object | 响应信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:200217） | 检查参数、稍后重试 |
| `40004` | 非法的参数 / OpenAppId为空（sub_code: isv.parameter-invalid:100001） | 检验token是否正确 |
| `50002` | 业务处理失败 / 系统内部错误（sub_code: isv.business-failed:200216） | 检查参数、稍后重试 |
| `50002` | 业务处理失败 / 门店店铺信息不匹配，请确认店铺（sub_code: isv.business-failed:200219） | 检验token是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_err": {
      "err_code": "0",
      "err_msg": "success"
    },
    "page": "0",
    "page_size": "20",
    "store_list": [
      {
        "address_info": {
          "detail": "联创街与爱沙路交叉口",
          "lbs_city": "杭州市",
          "lbs_city_code": "330100",
          "lbs_district": "余杭区",
          "lbs_district_code": "3301100000000",
          "lbs_province": "浙江省",
          "lbs_province_code": "33",
          "lbs_town": "/",
          "lbs_town_code": "/"
        },
        "contact": "12341234123",
        "distance": "48400.123",
        "distance_desc": "距您48.4km",
        "global_stock": "true",
        "lbs_info": {
          "latitude": "31.3",
          "longitude": "121.5"
        },
        "logo_img": "https://p3-ecom-qualification-sign.ecombdimg.com/tos-cn-i-6v",
        "open_time": {
          "custom": "周一至周五 08:00-20:30",
          "day_map": {}
        },
        "stock_infos": [
          {
            "product_id": "12341234",
            "sku_id": "12344321",
            "stock_num": "3",
            "store_id": "12341234"
          }
        ],
        "stock_num": "100",
        "store_id": "201500000",
        "store_name": "服饰自提测试门店2"
      }
    ],
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:200217",
  "sub_msg": "系统内部错误"
}
```

## 备注
