# instantShopping.marketing.addActivityProducts

> 添加商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.addActivityProducts` |
| 中文名 | 添加商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6381 |
| 更新日期 | `2024-05-22` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 是 | 活动id | `123` |
| `activity_type` | body | string | 是 | 活动类型，10：限时限量购，20：店铺券； 30：商品券 | `10` |
| `activity_sub_type` | body | string | 是 | 活动子类型， 101限时秒杀，102，普通降价促销 | `101` |
| `create_details` | body | array | 是 | 待创建的优惠明细，批量创建时多条detail必须属于同一个门店 | `` |
| `  └ main_product_id` | body | string | 否 | 主品id | `123` |
| `  └ main_sku_id` | body | string | 否 | 主skuId | `123` |
| `  └ activity_detail` | body | object | 否 | 优惠详情 | `` |
| `    └ stock_option` | body | object | 否 | 库存设置 | `` |
| `      └ use_max_limit` | body | boolean | 是 | true：实际库存小于活动库存时，使用实际库存作为活动库存 false：实际库存小于活动库存时，禁止提报 | `true` |
| `      └ activity_stock` | body | number | 是 | 提报使用的活动库存 | `123` |
| `    └ activity_price` | body | number | 否 | 活动价，单位：分 | `123` |
| `    └ limit_buy` | body | number | 否 | 每人限购 | `123` |
| `  └ sub_product_id` | body | string | 否 | 子品ID | `123` |
| `  └ sub_sku_id` | body | string | 否 | 子品SKUID | `123` |
| `  └ store_id` | body | number | 是 | 门店id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/List?app_key=your_appkey_here&method=afterSale.List&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_detail_list` | array | 成功创建的优惠明细 | `` |
| `fail_detail_list` | array | 失败创建的优惠明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

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
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
