# instantShopping.trade.freightDetail

> 即时零售运费模板详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-logistics.instantShopping.trade.freightDetail` |
| 中文名 | 即时零售运费模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1530/7423 |
| 更新日期 | `2025-04-24` |

## 接口说明

- 文档书: 物流发货API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `freight_id` | body | mixed | 否 | 运费模板id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.trade.freightDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "columns": [
        {
          "add_num": "1",
          "add_num_price": "1",
          "add_weight": "1",
          "add_weight_price": "0",
          "calculate_type": "2",
          "delivery_fulfillment_mode": "2",
          "end_time": "-",
          "first_num": "1",
          "first_num_price": "1",
          "first_weight": "1",
          "first_weight_price": "1",
          "fixed_amount": "1",
          "is_default": "1",
          "is_limited": "0",
          "is_over_free": "1",
          "max_sku_amount": "0",
          "min_sku_amount": "0",
          "over_amount": "1",
          "over_num": "1",
          "over_weight": "1",
          "province_infos": [
            {
              "children": [
                {
                  "children": [
                    {
                      "children": [
                        {
                          "id": "11000001"
                        }
                      ],
                      "id": "110000"
                    }
                  ],
                  "id": "1100"
                }
              ],
              "id": "11"
            }
          ],
          "reason": "-",
          "rule_type": "2"
        }
      ],
      "template": {
        "calculate_type": "2",
        "fixed_amount": "0",
        "id": "1",
        "product_city": "110000",
        "product_province": "11",
        "rule_type": "6",
        "template_name": "包邮",
        "transfer_type": "1"
      }
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
