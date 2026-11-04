# 根据策略ID获取单个策略信息

> address.getAftersaleStrategy — 根据策略ID获取单个策略信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据策略ID获取单个策略信息 |
| 文档地址 | `/docs/doudian/refund/refund-address-getAftersaleStrategy` |
| 接口 ID | `doudian.refund.address.getAftersaleStrategy` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/getAftersaleStrategy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6908 |
| 更新日期 | `2025-08-25` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `strategy_id` | body | string | 否 | 策略ID; | `必填，策略ID` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/getAftersaleStrategy?app_key=your_appkey_here&method=address.getAftersaleStrategy&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请输入正确的参数（sub_code: isv.parameter-invalid:4000） | 根据返回信息调整输入参数，如果多次调整后无法对接，可以寻求抖店帮助 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 重试，如果多次重试无法对接，可以通过提开放平台工单。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 重试，如果多次重试无法对接，可以通过提开放平台工单。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:100011） | 重试，如果多次重试无法对接，可以通过提开放平台工单。 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "address_list": [
        {
          "address": {
            "address": "北京市北京市海淀区海淀街道花园路牡丹园中兴大厦",
            "after_sale_note": "测试备注",
            "biz_id": "0",
            "biz_type": "0",
            "city_id": "110000",
            "city_name": "北京市",
            "common_phone": {
              "area_num": "400",
              "auxiliary_num": "1234",
              "main_num": "8888111",
              "num": "40088881111234"
            },
            "company_phone": {
              "num": "40088881111234",
              "phone_num": "40088881111234"
            },
            "create_time": "2024-09-25 16:33:15",
            "detail": "花园路牡丹园中兴大厦",
            "id": "32693731",
            "is_default": "1",
            "is_send_default": "1",
            "link_type": "2",
            "mobile": "400-8888111-1234",
            "phone": "13288889999",
            "province_id": "11",
            "province_name": "北京市",
            "shop_id": "77977",
            "street_id": "110108012",
            "street_name": "海淀街道",
            "town_id": "110108",
            "town_name": "海淀区",
            "update_time": "2024-09-25 22:04:14",
            "user_name": "xiaoming"
          },
          "bind_address_list": [
            {
              "city_id": "110000",
              "city_name": "北京市",
              "province_id": "11",
              "province_name": "北京市"
            }
          ]
        }
      ],
      "createtime": "1727252654",
      "related_product_count": "1",
      "shop_id": "77977",
      "strategy_description": "所有收货地区使用同一个退货地址",
      "strategy_id": "AFS7418493389946110223",
      "strategy_name": "测试策略-13",
      "strategy_type": "1",
      "strategy_type_name": "固定退货地址",
      "update_time": "1727271436"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4000",
  "sub_msg": "请输入正确的参数"
}
```

## 备注
