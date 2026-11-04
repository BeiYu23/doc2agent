# 查询订单维度快递可达及推荐服务

> logistics.getRecommendedAndDeliveryExpressByOrder — 查询订单维度快递可达及推荐服务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询订单维度快递可达及推荐服务 |
| 文档地址 | `/docs/doudian/logistics/logistics-logistics-getRecommendedAndDeliveryExpressByOrder` |
| 接口 ID | `doudian.logistics.logistics.getRecommendedAndDeliveryExpressByOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getRecommendedAndDeliveryExpressByOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2856 |
| 更新日期 | `2026-08-12` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sender_address` | body | object | 是 | 发货地址 | `` |
| `  └ country_code` | body | string | 否 | 1 | `1` |
| `  └ district_code` | body | string | 否 | 1 | `1` |
| `  └ zip_code` | body | string | 否 | 1 | `1` |
| `  └ city_name` | body | string | 是 | 市 | `北京市` |
| `  └ province_code` | body | string | 否 | 1 | `1` |
| `  └ street_code` | body | string | 否 | 1 | `1` |
| `  └ detail_address` | body | string | 是 | 详细地址，如果没有则传空字符串即可 | `123` |
| `  └ province_name` | body | string | 是 | 省 | `北京市` |
| `  └ city_code` | body | string | 否 | 1 | `1` |
| `  └ district_name` | body | string | 是 | 区 | `海淀区` |
| `  └ street_name` | body | string | 否 | 街道 | `中关村街道` |
| `  └ address_id` | body | mixed | 否 | 1 | `1` |
| `order_info_list` | body | array | 是 | 订单信息列表 | `` |
| `  └ product_type` | body | string | 否 | 产品类型，可不传 | `byte_pt` |
| `  └ express_list` | body | array | 否 | 物流商集合，不传默认：yuantong、zhongtong、yunda、shunfeng、jd、jtexpress、shentong | `['zhongtong','yundan','shunfeng']` |
| `  └ order_id` | body | string | 是 | 订单号 | `123` |
| `order_channel` | body | string | 否 | 订单平台来源编码，不传默认抖店 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getRecommendedAndDeliveryExpressByOrder?app_key=your_appkey_here&method=logistics.getRecommendedAndDeliveryExpressByOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:4006） | 根据错误描述检查参数 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:4007） | 一般重试可解决，若一直报错请联系oncall |
| `20000` | 系统错误 / 查询订单信息失败（sub_code: isp.service-error:15000） | 一般重试可解决，若一直报错请联系oncall |
| `50002` | 业务处理失败 / 订单信息不存在（sub_code: isv.business-failed:15002） | 检查传入订单号是否是抖店正确订单号 |
| `40004` | 非法的参数 / 用户未开通该服务（sub_code: isv.parameter-invalid:100001） | 抖店后台-物流服务-开通发货探查服务 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "express_info_list": [
          {
            "ccr_Info": {
              "ccr_rate": "0.001",
              "level_percent": "0.2",
              "optimized_percent": "0.34"
            },
            "collect_sign_info": {
              "avg_cost_hours": "60.10",
              "level_percent": "23.86",
              "optimized_percent": "6.1"
            },
            "express": "zhongtong",
            "is_deliverable": "true",
            "is_recommended": "true",
            "is_shop_eBill": "true",
            "rank_route": "1",
            "recommend_reason": "推荐原因",
            "tail_Info": {
              "level_percent": "0.34",
              "optimized_percent": "0.2",
              "tail_rate": "0.001"
            },
            "undeliverable_reason": "服务不可达"
          }
        ],
        "order_id": "123",
        "order_privilege_info_list": [
          {
            "code": "priority_delivery",
            "label": "优先发货",
            "reason": "用户负反馈率高"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4006",
  "sub_msg": "参数错误"
}
```

## 备注
