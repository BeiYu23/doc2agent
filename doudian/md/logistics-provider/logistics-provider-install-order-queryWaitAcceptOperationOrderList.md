# install.order.queryWaitAcceptOperationOrderList

> 未接单的实操单据列表查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.queryWaitAcceptOperationOrderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/queryWaitAcceptOperationOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7713 |
| 更新日期 | `2026-08-10` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_entity_code` | body | string | 否 | 服务实体编码 | `"test"` |
| `page_no` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 页大小 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.order.queryWaitAcceptOperationOrderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `operation_order_list` | array | 待接单实操单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "operation_order_list": [
      {
        "buyer_id": "\"12434\"",
        "buyer_info": {
          "appointment_time": "\"2024-08-21 17:16:20\"",
          "buyer_address": {
            "city_code": "\"\"",
            "city_name": "\"\"",
            "district_code": "\"\"",
            "district_name": "\"\"",
            "encrypt_detail_address": "\"\"",
            "encrypt_latitude": "\"\"",
            "encrypt_longitude": "\"\"",
            "province_code": "\"11\"",
            "province_name": "\"\"",
            "street_code": "\"\"",
            "street_name": "\"\""
          },
          "encrypt_buyer_name": "\"XXX\"",
          "encrypt_virtual_number": "\"12345678888\""
        },
        "buyer_type": "5",
        "channel_code": "\"DouYinDianShang\"",
        "is_user_paid": "true",
        "logistics_info": {
          "expect_delivery_time": "\"\"2006-01-02 15:04:05\"\"",
          "express_info_list": [
            {
              "send_time": "0",
              "sign_time": "0",
              "waybill_no": "\"SF353464654657\""
            }
          ]
        },
        "operation_info": {
          "check_in_time": "\"2023-09-21 14:00:00\"",
          "finish_time": "\"2023-09-21 14:00:00\"",
          "operator_name": "\"XXXX\"",
          "operator_phone": "\"12434566666\"",
          "real_appointment_time": "\"2023-09-21 14:00:00\""
        },
        "operation_no": "\"BSO23245325544\"",
        "operation_time": "\"2024-08-21 17:16:20\"",
        "order_info": {
          "real_shop_order_list": [
            {
              "real_sku_order_list": [
                {
                  "sku_order_no": "\"62232534453677112\""
                }
              ],
              "shop_order_no": "\"62232534453677112\""
            }
          ],
          "shop_order_no": "\"62232534453677112\"",
          "sku_order_no": "\"62232534453677112\""
        },
        "order_no": "\"6221325364546577\"",
        "product_info": {
          "brand_name": "\"XXXX\"",
          "category_info": {
            "first_category_id": "\"\"",
            "first_category_name": "\"\"",
            "forth_category_id": "\"\"",
            "forth_category_name": "\"\"",
            "second_category_id": "\"\"",
            "second_category_name": "\"\"",
            "third_category_id": "\"\"",
            "third_category_name": "\"\""
          },
          "name": "\"冰箱\"",
          "sku_info_list": [
            {
              "shop_custom_sku_code": "\"2435443\"",
              "sku_id": "\"\"",
              "sku_img_url": "\"\"",
              "sku_name": "\"\"",
              "specification_info": "\"\""
            }
          ],
          "specification_info": "\"\"",
          "url": "\"https://XXXXXXXX.com\""
        },
        "quotation_info": {
          "install_method": "\"到店安装\"",
          "property_info_list": [
            {
              "prop_id": "\"3254\"",
              "prop_name": "\"\"",
              "prop_type": "5",
              "prop_value": "\"\""
            }
          ],
          "real_product_category_info": {
            "first_category_id": "\"\"",
            "first_category_name": "\"\"",
            "forth_category_id": "\"\"",
            "forth_category_name": "\"\"",
            "second_category_id": "\"\"",
            "second_category_name": "\"\"",
            "third_category_id": "\"\"",
            "third_category_name": "\"\""
          }
        },
        "service_code": "\"SVC-WBINSTALL\"",
        "service_entity_code": "\"test\"",
        "service_mode": "4",
        "service_num": "5",
        "service_order_info": {
          "shop_order_no": "\"62232534453677112\"",
          "sku_order_no": "\"62232534453677112\""
        },
        "service_shop_info": {
          "shop_id": "\"123456\"",
          "shop_name": "\"XXXXXX旗舰店\""
        },
        "settle_info": {
          "settle_amount": "10000",
          "settle_time": "\"2006-01-02 12:12:12\"",
          "settle_type": "1"
        },
        "shop_info": {
          "shop_id": "\"1234\"",
          "shop_name": "\"XXXXXX旗舰店\""
        }
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
