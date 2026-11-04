# trade.GetFreightTemplateByTemplateID

> 小时达查询运费模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.trade.GetFreightTemplateByTemplateID` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/GetFreightTemplateByTemplateID` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/4675 |
| 更新日期 | `2023-12-15` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | mixed | 是 | 模板ID | `29877897` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/GetFreightTemplateByTemplateID?app_key=your_appkey_here&method=trade.GetFreightTemplateByTemplateID&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `freight_template_vo_list` | array | 运费模板列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "freight_template_vo_list": [
      {
        "base": [
          {
            "price": "100"
          }
        ],
        "create_time": "1694088422",
        "distance": [
          {
            "add_distance": "1000",
            "add_price": "100",
            "first_distance": "1000"
          }
        ],
        "free": [
          {
            "amount": "100"
          }
        ],
        "freight_mode": "4",
        "id": "100000",
        "interval": [
          {
            "add_price": "100",
            "time_end": "36000",
            "time_start": "0"
          }
        ],
        "name": "测试模板名称",
        "shipping_address": {
          "city_id": "110000",
          "coordinate": {
            "geo_hash": "1000",
            "latitude": "10.000",
            "longitude": "10.000"
          },
          "province_id": "11",
          "street_id": "110108011",
          "town_id": "110108"
        },
        "update_time": "1694088422",
        "weight": [
          {
            "add_price": "100",
            "add_weight": "1000",
            "first_weight": "1000"
          }
        ]
      }
    ]
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
