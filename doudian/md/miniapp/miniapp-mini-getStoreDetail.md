# mini.getStoreDetail

> 小程序c端获取门店信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.getStoreDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/getStoreDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7261 |
| 更新日期 | `2025-02-21` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id，不是商品的storeid | `201581626` |
| `lbs_info` | body | object | 否 | wgs84经纬度 | `` |
| `  └ longitude` | body | string | 否 | 纬度 | `31.317514` |
| `  └ latitude` | body | string | 否 | 经度 | `121.508568` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/getStoreDetail?app_key=your_appkey_here&method=mini.getStoreDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store` | object | 门店信息 | `` |
| `custom_err` | object | 接口返回错误信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:200216） | 稍后重试 |
| `40004` | 非法的参数 / OpenAppId为空（sub_code: isv.parameter-invalid:100001） | 检查app_key是否正确 |
| `10001` | 请求部分失败 / 门店信息为空（sub_code: isv.business-part-failed:200218） | 检查输入是否正确 |
| `40004` | 非法的参数 / 店铺id不匹配（sub_code: isv.parameter-invalid:200219） | 请确认使用账号 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_err": {
      "err_code": "0",
      "err_msg": "success"
    },
    "store": {
      "address_info": {
        "detail": "凤起路111号",
        "lbs_city": "杭州市",
        "lbs_city_code": "330100",
        "lbs_district": "余杭区",
        "lbs_district_code": "3301100000000",
        "lbs_province": "浙江省",
        "lbs_province_code": "33",
        "lbs_town": "/",
        "lbs_town_code": "/"
      },
      "contact": "12345678901",
      "distance": "48402.19774960337",
      "distance_desc": "距您48.4km",
      "is_open_now": "true",
      "lbs_info": {
        "latitude": "31.000",
        "longitude": "121.000"
      },
      "logo_img": "https://p6-ecom-qualification-sign.ecombdimg.com/tos-cn-i-6v",
      "open_time": {
        "custom": "/",
        "day_map": {}
      },
      "store_id": "0",
      "store_name": "服饰自提测试门店1"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:200216",
  "sub_msg": "系统内部错误"
}
```

## 备注
