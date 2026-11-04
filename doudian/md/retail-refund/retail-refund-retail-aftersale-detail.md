# 售后

> retail.aftersale.detail — 售后详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 售后 |
| 文档地址 | `/docs/doudian/retail-refund/retail-refund-retail-aftersale-detail` |
| 接口 ID | `doudian.retail-refund.retail.aftersale.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/retail/aftersale/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1548/6891 |
| 更新日期 | `2024-12-23` |

## 接口说明

- 文档书: 售后管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_id` | body | string | 是 | 售后单ID | `146601583232796600` |
| `need_operation_record` | body | boolean | 否 | 是否需要操作记录 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/retail/aftersale/detail?app_key=your_appkey_here&method=retail.aftersale.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `process_info` | object | 售后单及相关信息 | `` |
| `order_info` | object | 售后单关联订单信息 | `` |
| `signed` | boolean | 发起售后时订单是否已送达，true：已送达，false：未送达 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 20309019:无效的店铺ID，请检查此店铺ID是否正确并重试（sub_code: isv.business-failed:20309019） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 12001:无效的店铺ID，请检查此店铺ID是否正确并重试（sub_code: isv.business-failed:12001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 20309000:关联用户信息获取失败，请检查售后单号是否正确，确认无误后重试（sub_code: isv.business-failed:20309000） | 请参考能力文档传入合法参数 |

## 响应示例

成功：

```json
{
  "data": {
    "order_info": {
      "main_status": "103",
      "shop_order_id": "12345",
      "sku_order_infos": [
        {
          "after_sale_item_count": "1",
          "create_time": "1735660800",
          "custom_property_list": [
            {
              "group_name": "温度",
              "property_details": [
                {
                  "name": "正常冰"
                }
              ]
            }
          ],
          "given_sku_details": [
            {
              "item_order_num": "1",
              "product_id": "361124732503867950",
              "product_name": "产品名",
              "shop_sku_code": "123",
              "sku_order_id": "4866736775786465058"
            }
          ],
          "is_oversea_order": "0：不是 1：是",
          "item_quantity": "1",
          "item_sum_amount": "1000",
          "main_status": "103",
          "order_status": "4:\\\"订单取消\\\"",
          "pay_amount": "1000",
          "pay_type": "0 : \\\"货到付款\\\" 1：\\\"在线支付\\\"",
          "post_amount": "100",
          "product_id": "12345",
          "product_image": "商品图片链接",
          "product_name": "\\\"耐克球鞋\\\"",
          "promotion_amount": "100",
          "shop_sku_code": "\\\"12345\\\"",
          "sku_id": "12345",
          "sku_order_id": "12345",
          "sku_pay_amount": "900",
          "sku_spec": [
            {
              "name": "\\\"数量\\\"",
              "value": "12"
            }
          ],
          "tags": [
            {
              "tag_detail": "\\\"极速退\\\"",
              "tag_detail_en": "\\\"refund_auto_deal\\\"",
              "tag_link_url": "\\\"https://school.jinritemai.com/doudian/web/article/101792?from=shop_article\\\""
            }
          ],
          "tax_amount": "100"
        }
      ]
    },
    "process_info": {
      "after_sale_info": {
        "after_sale_apply_count": "1",
        "after_sale_id": "6965315853751632172",
        "after_sale_order_type": "1",
        "after_sale_status": "6",
        "after_sale_status_desc": "售后成功",
        "after_sale_type": "0",
        "after_sale_type_text": "补寄",
        "aftersale_status_to_final_time": "1735660800",
        "aftersale_tags": [
          {
            "placeholder": {},
            "tag_detail": "风险预警",
            "tag_detail_en": "risk_warning",
            "tag_link_url": "略"
          }
        ],
        "agree_refuse_sign": "1",
        "apply_role": "1",
        "apply_time": "1735660800",
        "auto_audit_bits": "[1, 2]",
        "deduction_amount": "10000",
        "disable_coupon_id": "12345",
        "evidence": "[ \"http://p6-aftersale-sign.ecombdimg.com/douyin-user-image-file/869bed93812154773403174c5feae63c~tplv-51d71q3p2z-q75-jpeg.jpeg?x-expires=1676015949\\u0026x-signature=R%2Fbr7Gcl3s2Opfboss66qdY2CWc%3D\"]",
        "got_pkg": "1",
        "kol_discount_return_amount": "100",
        "kol_discount_return_status": "1",
        "kol_post_discount_return_amount": "100",
        "need_return_count": "1",
        "part_type": "1",
        "platform_discount_return_amount": "100",
        "platform_discount_return_status": "1",
        "post_discount_return_amount": "100",
        "post_discount_return_status": "1",
        "post_duty": "1",
        "real_refund_amount": "300",
        "reason": "无理由退款",
        "reason_code": "2",
        "reason_remark": "不喜欢这件商品",
        "refund_fail_reason": "\\\"用户账户异常，平台处理中\\\"",
        "refund_packing_charge_amount": "100",
        "refund_post_amount": "10",
        "refund_promotion_amount": "10",
        "refund_status": "1",
        "refund_time": "1735660800",
        "refund_total_amount": "1000",
        "refund_type": "无需退款",
        "refund_type_text": "无需退款",
        "return_address": {
          "city": {
            "id": "432",
            "name": "杭州市"
          },
          "detail": "新华书店门口左转一米",
          "landmark": "\"\"",
          "province": {
            "id": "32",
            "name": "浙江省"
          },
          "street": {
            "id": "43",
            "name": "解放路"
          },
          "town": {
            "id": "432",
            "name": "西湖区"
          }
        },
        "return_address_id": "123123",
        "return_book_info": {
          "book_time_begin": "09:00",
          "book_time_end": "13:00",
          "return_type": "1"
        },
        "return_method": "1",
        "shop_discount_return_amount": "10",
        "shop_post_discount_return_amount": "100",
        "status_deadline": "1735660800",
        "store_id": "121323",
        "store_name": "海底捞昌阳店",
        "update_time": "1735660800"
      },
      "after_sale_service_tag": {
        "after_sale_service_tag": [
          {
            "tag_detail": "\\\"7天\\\"",
            "tag_detail_en": "\\\"supply_7day_return\\\"",
            "tag_link_url": "\\\"https://school.jinritemai.com/doudian/web/article/101835?from=shop_article\\\""
          }
        ]
      },
      "after_sale_shop_remarks": [
        {
          "after_sale_id": "54321",
          "create_time": "173566080",
          "operator": "\\\"小亮\\\"",
          "order_id": "12345",
          "remark": "\\\"你好\\\""
        }
      ],
      "arbitrate_info": {
        "arbitrate_blame": "1:商家责任,2:买家责任,3:双方有责,4:平台责任,5:达人责任",
        "arbitrate_conclusion": "0",
        "arbitrate_create_time": "1735660800",
        "arbitrate_evidence": {
          "describe": "仲裁描述",
          "images": "仲裁图片示例"
        },
        "arbitrate_evidence_tmpl": {
          "dead_line": "1735660800",
          "describe": "仲裁描述",
          "images": "仲裁图片示例"
        },
        "arbitrate_id": "12345",
        "arbitrate_opinion": "仲裁原因描述",
        "arbitrate_status": "0 : \\\"无需仲裁\\\"",
        "arbitrate_status_deadline": "1735660800",
        "arbitrate_update_time": "1735660800",
        "is_required_evidence": "1 : \\\"需要上传凭证\\\""
      },
      "record_logs_list": [
        {
          "action": "仲裁举证",
          "all_evidence": [
            {
              "desc": "描述",
              "type": "1",
              "urls": "图片链接"
            }
          ],
          "desc_kvs": [
            {
              "highlight": "false",
              "key": "举证说明",
              "notice": "空",
              "value": "测试"
            }
          ],
          "images": "图片链接",
          "operator": "商家",
          "role": "2",
          "text": "买家举证",
          "time": "2022-09-05 21:34:24"
        }
      ]
    },
    "signed": "true"
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
  "sub_code": "isv.business-failed:5000001",
  "sub_msg": "业务系统异常，请联系开平人员"
}
```

## 备注
