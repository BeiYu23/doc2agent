# 判断用户是否可以参加活动

> mini.activity.userCanRegister — 判断用户是否可以参加活动

| 元信息 | 值 |
| --- | --- |
| 中文名 | 判断用户是否可以参加活动 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-activity-userCanRegister` |
| 接口 ID | `doudian.miniapp.mini.activity.userCanRegister` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/userCanRegister` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6659 |
| 更新日期 | `2024-08-13` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 否 | 活动id | `活动id` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/List?app_key=your_appkey_here&method=afterSale.List&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | true表示用户通过前置预校验 | `true` |
| `register_token` | string | 预注册token 在调用注册接口时需要传入 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 暂无购买资格（sub_code: isv.business-failed:606010026） | 暂无购买资格 |
| `50002` | 业务处理失败 / 活动暂未上线（sub_code: isv.business-failed:605030022） | 活动暂无开始 |
| `50002` | 业务处理失败 / 活动暂无开始（sub_code: isv.business-failed:605030014） | 活动暂无开始 |
| `50002` | 业务处理失败 / 605030008:活动已失效（sub_code: isv.business-failed:605030008） | 605030008:活动已失效 |
| `50002` | 业务处理失败 / 606010000:入参activityId非法（sub_code: isv.business-failed:606010000） | 606010000:入参activityId非法 |

## 响应示例

成功：

```json
{
  "data": {
    "has_more": "true",
    "items": [
      {
        "aftersale_info": {
          "aftersale_id": "6986853269519810849",
          "aftersale_num": "1",
          "aftersale_order_type": "1",
          "aftersale_refund_type": "0",
          "aftersale_status": "11",
          "aftersale_status_to_final_time": "1626753592",
          "aftersale_sub_type": "8001",
          "aftersale_tags": [
            {
              "placeholder": {},
              "tag_detail": "风险预警",
              "tag_detail_en": "risk_warning",
              "tag_detail_text": "该售后单【xxx预警原因】请根据物流/商品状态进行核实。若确认有风险，请及时保存举证${relate_doc}，可在${asset_prevent}操作批量拒绝售后；若无风险，可同意售后。",
              "tag_link_url": "略"
            }
          ],
          "aftersale_type": "0",
          "apply_time": "1626753592",
          "arbitrate_blame": "1:商家责任,2:买家责任,3:双方有责,4:平台责任,5:达人责任",
          "arbitrate_status": "0",
          "auto_audit_bits": "[1, 2]",
          "create_time": "1626753592",
          "exchange_logistics_company_name": "韵达快递",
          "exchange_sku_info": {
            "code": "\"10000\"",
            "name": "\"xxx\"",
            "num": "1",
            "out_sku_id": "\"10000\"",
            "out_warehouse_id": "\"10000\"",
            "price": "\"100\"",
            "sku_id": "\"1709160688834615\"",
            "spec_desc": "\"xx/xx/xx\"",
            "supplier_id": "\"10000\"",
            "url": "\"http://xxxxx\""
          },
          "got_pkg": "1",
          "is_agree_refuse_sign": "1",
          "left_urge_sms_count": "0",
          "order_logistics": [
            {
              "company_code": "shunfeng",
              "company_name": "顺丰",
              "logistics_state": "6",
              "logistics_time": "1637586290",
              "tracking_no": "SF12345678910"
            }
          ],
          "part_type": "0",
          "reason_second_labels": [
            {
              "code": "1",
              "name": "衣服买大"
            }
          ],
          "refund_amount": "20",
          "refund_post_amount": "0",
          "refund_status": "1",
          "refund_tax_amount": "0",
          "refund_type": "0",
          "related_id": "\"4821780700279174718\"",
          "remark": "买家不想要了",
          "return_logistics_code": "\"XY123123123\"",
          "return_logistics_company_name": "顺丰速运",
          "return_promotion_amount": "0",
          "risk_decision_code": "0",
          "risk_decision_description": "\"\"",
          "risk_decision_reason": "\"\"",
          "status_deadline": "1626926420",
          "store_id": "3592",
          "store_name": "xxx朝阳分店",
          "update_time": "1626860666"
        },
        "order_info": {
          "order_flag": "0",
          "related_order_info": [
            {
              "aftersale_item_num": "1",
              "aftersale_pay_amount": "20",
              "aftersale_post_amount": "0",
              "aftersale_tax_amount": "0",
              "create_time": "1626753467",
              "delivery_infos": [
                {
                  "info_type": "",
                  "info_unit": "",
                  "info_value": ""
                }
              ],
              "given_sku_order_ids": "4863025593329976686",
              "is_oversea_order": "0",
              "item_num": "1",
              "logistics_code": "\"RABBIT123123\"",
              "logistics_company_name": "顺丰速运",
              "order_status": "3",
              "pay_amount": "20",
              "post_amount": "0",
              "price": "20",
              "product_id": "9999888777666",
              "product_image": "https://bytedance.com/image/rabbit.jpg",
              "product_name": "小兔子T恤",
              "promotion_pay_amount": "0",
              "shop_sku_code": "\"\"",
              "sku_order_id": "\"4821780700279174718\"",
              "sku_spec": [
                {
                  "name": "颜色",
                  "value": "白"
                }
              ],
              "tags": [
                {
                  "tag_detail": "超级售后",
                  "tag_detail_en": "super_after_sale",
                  "tag_link_url": "http://what_is_super_after_sale.bytedance.com/faq"
                }
              ],
              "tax_amount": "0"
            }
          ],
          "shop_order_id": "\"4821780700279174718\""
        },
        "seller_logs": [
          {
            "content": "\"买家觉得小兔子太可爱了，不想要了\"",
            "create_time": "2001-01-01 03:04:05",
            "op_name": "\"兔子店铺CEO\"",
            "star": "0"
          }
        ],
        "text_part": {
          "aftersale_refund_type_text": "\"保证金\"",
          "aftersale_status_text": "\"待商家审核\"",
          "aftersale_type_text": "\"退货退款\"",
          "arbitrate_status_text": "\"\"",
          "bad_item_text": "\"\"",
          "logistics_text": "\"已发货\"",
          "reason_text": "\"无理由退款\"",
          "return_logistics_text": "\"已发货\""
        }
      }
    ],
    "page": "0",
    "size": "10",
    "total": "1025"
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
  "sub_code": "isv.business-failed:606010026",
  "sub_msg": "暂无购买资格"
}
```

## 备注
