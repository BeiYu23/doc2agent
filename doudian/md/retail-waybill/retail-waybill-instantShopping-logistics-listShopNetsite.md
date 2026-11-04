# instantShopping.logistics.listShopNetsite

> 查询商家和物流商的订购关系以及物流单号使用情况

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-waybill.instantShopping.logistics.listShopNetsite` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1578/7240 |
| 更新日期 | `2025-04-23` |

## 接口说明

- 文档书: 电子面单API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id | `123` |
| `logistics_code` | body | string | 否 | 物流商服务编码 | `shunfeng` |
| `out_warehouse_id` | body | mixed | 否 | 发货仓id | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logistics.listShopNetsite&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `netsites` | array | 网点信息列表 | `` |
| `company` | string | 快递公司编码 | `顺丰` |
| `company_type` | mixed | 物流服务商业务类型 1：直营 2：加盟 3：落地配 4：直营带网点 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 4006:店铺ID非法（sub_code: isv.business-failed:4006） | 请检查您的店铺id是否正确 |
| `50002` | 业务处理失败 / 40006:请传入正确的门店id（sub_code: isv.business-failed:40006） | 请传入正确的门店id |
| `50002` | 业务处理失败 / 40001:无效的门店信息（sub_code: isv.business-failed:40001） | 无效的门店信息 |
| `50002` | 业务处理失败 / 50040:系统开小差了，请稍后重试（sub_code: isv.business-failed:50040） | 系统开小差了，请稍后重试 |
| `50002` | 业务处理失败 / 1004:Internal Server Error（sub_code: isv.business-failed:1004） | 系统开小差了，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "company": "顺丰",
    "company_type": "1",
    "netsites": [
      {
        "allocated_quantity": "1",
        "amount": "1",
        "cancelled_quantity": "1",
        "company": "shunfeng",
        "company_type": "1",
        "ebill_type": "0",
        "netsite_code": "1",
        "netsite_name": "E世界",
        "out_warehouse_id": "1234",
        "product_type": "[]",
        "recycled_quantity": "1",
        "sender_address": [
          {
            "address_type": "0",
            "city_name": "北京市",
            "detail_address": "E世界",
            "district_name": "海淀区",
            "province_name": "北京",
            "street_name": "E世界"
          }
        ],
        "store_id": "123",
        "store_name": "蔬果店",
        "warehouse_name": "北京仓"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "4006:店铺ID非法"
}
```

## 备注
