# address.listAftersaleStrategy

> 地址策略列表接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.address.listAftersaleStrategy` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/listAftersaleStrategy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6907 |
| 更新日期 | `2024-10-08` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_by_field` | body | string | 否 | 排序的字段;create_time-创建时间; update_time-更新时间; | `create_time` |
| `size` | body | mixed | 否 | 每页的条数, 每页最大不超过20个。当前单个商家只允许创建1000条策略，page * size > 1000会被拦截。 | `20` |
| `order_by` | body | string | 否 | 升序还是排序；asc-升序；desc-降序; | `asc` |
| `page` | body | mixed | 否 | 页码， 从1开始,表示第1页; | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/listAftersaleStrategy?app_key=your_appkey_here&method=address.listAftersaleStrategy&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `size` | mixed | 每页数量; | `2` |
| `strategy_list` | array | 策略列表; | `` |
| `total` | mixed | 总量; | `12` |
| `page` | mixed | 页数; | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 根据返回的错误信息调整参数进行重试，确认参数无问题并且重试不成功，在开放平台提工单咨询 |
| `40004` | 非法的参数 / 请输入正确的参数（sub_code: isv.parameter-invalid:4000） | 根据返回的错误信息调整参数进行重试，确认参数无问题并且重试不成功，在开放平台提工单咨询 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 根据返回的错误信息调整参数进行重试，确认参数无问题并且重试不成功，在开放平台提工单咨询 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:7000） | 根据返回的错误信息调整参数进行重试，确认参数无问题并且重试不成功，在开放平台提工单咨询 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:100011） | 根据返回的错误信息调整参数进行重试，确认参数无问题并且重试不成功，在开放平台提工单咨询 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "1",
    "size": "2",
    "strategy_list": [
      {
        "address_list": [
          {
            "address": {
              "address": "北京市北京市海淀区海淀街道花园路牡丹园中兴大厦",
              "after_sale_note": "拒绝到付",
              "biz_id": "0",
              "biz_type": "0",
              "city_id": "110000",
              "city_name": "北京市",
              "common_phone": {
                "area_num": "0635",
                "auxiliary_num": "1111",
                "main_num": "5781308",
                "num": "0635-5781308-1111"
              },
              "company_phone": {
                "num": "40088881111234",
                "phone_num": "40088881111234"
              },
              "create_time": "2024-09-25 16:33:15",
              "detail": "花园路牡丹园中兴大厦",
              "error_type": "0",
              "id": "32693731",
              "is_default": "1",
              "is_send_default": "1",
              "link_type": "1",
              "mobile": "0635-5781308",
              "phone": "13288889999",
              "province_id": "11",
              "province_name": "北京市",
              "shop_id": "77977",
              "street_id": "110108012",
              "street_name": "海淀街道",
              "town_id": "110108",
              "town_name": "海淀区",
              "update_time": "2024-09-25 16:38:47",
              "user_name": "xiaoming"
            }
          }
        ],
        "createtime": "1727252654",
        "related_product_count": "1",
        "shop_id": "77977",
        "strategy_description": "所有收货地区使用同一个退货地址",
        "strategy_id": "AFS7418493389946110223",
        "strategy_name": "静态策略-1",
        "strategy_type": "1",
        "strategy_type_name": "固定退货地址",
        "update_time": "1727253300"
      }
    ],
    "total": "12"
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
  "sub_code": "isv.business-failed:5001",
  "sub_msg": "系统繁忙，请稍后重试"
}
```

## 备注
