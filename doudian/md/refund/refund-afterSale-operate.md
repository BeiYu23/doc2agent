# 售后审核接口聚合版

> afterSale.operate — 售后审核接口聚合版

| 元信息 | 值 |
| --- | --- |
| 中文名 | 售后审核接口聚合版 |
| 文档地址 | `/docs/doudian/refund/refund-afterSale-operate` |
| 接口 ID | `doudian.refund.afterSale.operate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/operate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/560 |
| 更新日期 | `2026-09-22` |

## 接口说明

- 文档书: 售后退款API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `type` | body | mixed | 是 | 操作类型；枚举值说明文档：https://op.jinritemai.com/docs/question-docs/93/2752 | `111` |
| `items` | body | array | 是 | 操作售后详情 | `` |
| `  └ aftersale_id` | body | string | 是 | 售后单号 | `6959800000297566494` |
| `  └ remark` | body | string | 否 | 操作评论，拒绝操作必填 | `商品有污渍，影响二次销售` |
| `  └ logistics` | body | object | 否 | 同意退货/同意换货物流信息，当前type=101，301，311是该集合需要传值。 | `` |
| `    └ logistics_code` | body | string | 否 | 物流单号（快递单号），仅type=311仅换货时需要填入 | `YT31368712931` |
| `    └ company_code` | body | string | 否 | 物流公司code，使用【/order/logisticsCompanyList】接口获取；type=311仅换货时需要填入 | `yuantong` |
| `    └ receiver_address_id` | body | mixed | 否 | 商家收件地址id（推荐使用），须通过【/address/list】获取【address_id】填入。商家在同意换货/退货时，可以传入该地址id，对应的地址会买家展示进行商品退回； | `95251` |
| `    └ after_sale_address_detail` | body | object | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段，商家收货地址详情； | `` |
| `      └ street_id` | body | mixed | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段街道id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `12` |
| `      └ city_name` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段市；需要使用【/address/getAreasByProvince】接口响应参数获取 | `北京` |
| `      └ mobile` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段联系电话，支持手机号和固定电话；固定电话需要传入区号。注意：区号和号码之间一定要传入“-”传值示例：0571-1234567；否则会报错电话号码不合法。 | `17777777777` |
| `      └ province_name` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段省；使用【/address/getProvince】接口获取 | `北京` |
| `      └ street_name` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段街道名称 | `xxx街道` |
| `      └ town_id` | body | mixed | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段区id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `01` |
| `      └ town_name` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段区；需要使用【/address/getAreasByProvince】接口响应参数获取 | `海淀` |
| `      └ province_id` | body | mixed | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段省id；使用【/address/getProvince】接口获取 | `10` |
| `      └ user_name` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段收件人 | `张三` |
| `      └ city_id` | body | mixed | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段市id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `10` |
| `      └ detail` | body | string | 否 | 【该字段将在2023年8月31日下线】，请尽快切换使用receiver_address_id字段地址详情 | `北京市海淀区丹棱街1号305` |
| `    └ serial_nos` | body | array | 否 | 无人机换货sn码 | `无人机sn码` |
| `    └ sender_address_id` | body | mixed | 否 | 已废弃字段（废弃时间2022-06-10）发件地址id | `95252` |
| `  └ evidence` | body | array | 否 | 操作凭证编码，当【afterSale/rejectReasonCodeList】接口响应参数evidence_need=Y时，该参数必填；使用【afterSale/rejectReasonCodeList】接口获取响应参数中的reject_reason_code字段。 | `` |
| `    └ desc` | body | string | 否 | 凭证描述 | `过敏部位图片` |
| `    └ type` | body | mixed | 否 | 凭证类型，1:图片，2:视频(暂不支持)，3:音频(暂不支持展示)，4:文字(暂不支持展示)。“用户可见备注”为remark字段 | `0` |
| `    └ url` | body | string | 否 | 凭证url | `http://xxxxxxxx.jpg` |
| `  └ repair_type` | body | mixed | 否 | 维修类型（1-原商品维修；2-商品换新） | `1` |
| `  └ reason` | body | string | 否 | 操作原因，拒绝操作必填 | `商品有破损` |
| `  └ update_time` | body | mixed | 否 | 用于校验售后单版本是不是最新的版本，防止售后单变更且open侧审核通过导致资损。不传就不校验，传入后就会校验isv传入的售后单版本是不是最新的版本。 需要使用【/afterSale/Detail】接口返回的update_time字段或使用售后消息推送中的update_time字段 | `0` |
| `  └ reject_reason_code` | body | mixed | 否 | 售后拒绝原因码，拒绝时必填填。通过/afterSale/rejectReasonCodeList获取 | `1` |
| `store_id` | body | string | 否 | 门店ID；抖超小时达业务使用； | `门店ID` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/operate?app_key=your_appkey_here&method=afterSale.operate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 审核结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误，电话号码不合法（sub_code: isv.parameter-invalid:11000） | 检查电话号码后重试 |
| `20000` | 系统错误 / 存在无效的售后单（sub_code: isp.service-error:10000） | 检查售后单后重试 |
| `20000` | 系统错误 / 返回内容为空，重试后若错误继续存在，请联系平台（sub_code: isp.service-error:10002） | 重试 |
| `50002` | 业务处理失败 / 操作失败（sub_code: isv.business-failed:11005） | 检查后重试 |
| `50002` | 业务处理失败 / 11001:暂不支持通过OPEN处理，请登录抖店后台人工审核售后单。如有疑问，请联系平台客服。（sub_code: isv.business-failed:11001） | 无法重试解决 |
| `50002` | 业务处理失败 / 售后状态错误（sub_code: isv.business-failed:20309541） | 重新同步获取&检查售后数据，重试无效 |
| `50002` | 业务处理失败 / 12000:系统错误（sub_code: isv.business-failed:12000） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / SN码被占用（sub_code: isv.business-failed:10011） | 检查SN码 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "aftersale_id": "6959800000297566494",
        "sn_error": {
          "action": [
            {
              "action": {
                "action_i_d": "特殊动作",
                "apply_freight_info": {
                  "node_id": "节点ID",
                  "node_key": "节点Key",
                  "node_val": "节点Value",
                  "order_id": "订单ID",
                  "process_instance_id": "流程实例ID",
                  "user_id": "用户ID"
                },
                "batch_select_reason_drawer": {
                  "biz_params": "获取拆分批量申请页schema的参数",
                  "page_key": "拆分批量申请页page key",
                  "select_reason_sku_orders": [
                    {}
                  ],
                  "title": "title"
                },
                "combine_pop_up_item": {
                  "button_list": [
                    {}
                  ],
                  "order_infos": [
                    {}
                  ],
                  "sub_title": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "title": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  }
                },
                "compensate_drawer": {
                  "compensate_by_coupon": {
                    "coupon_detail_list": [
                      {}
                    ],
                    "coupon_schema": {},
                    "desc": "主标题"
                  },
                  "title": "主标题"
                },
                "confirm_exception_info": {
                  "aftersale_id": "aftersale_id",
                  "exception_scene": "exception_scene"
                },
                "deduction_amount_info": {
                  "apply_amount": {
                    "action": {},
                    "desc": {},
                    "full_line_text": {},
                    "side_click_icon": "点击图标，如小问号",
                    "side_sub_text": {},
                    "side_text": {},
                    "side_text_list": [
                      {}
                    ],
                    "tag": "文案旁的标签，eg:已赔付",
                    "text": "文案，eg:运费险"
                  },
                  "deduction_amount": [
                    {}
                  ],
                  "real_amount": {
                    "action": {},
                    "desc": {},
                    "full_line_text": {},
                    "side_click_icon": "点击图标，如小问号",
                    "side_sub_text": {},
                    "side_text": {},
                    "side_text_list": [
                      {}
                    ],
                    "tag": "文案旁的标签，eg:已赔付",
                    "text": "文案，eg:运费险"
                  },
                  "title": "标题，如「金额扣减明细」"
                },
                "drawer": {
                  "button": {
                    "action": {},
                    "block": "是否允许点击",
                    "desc": "按钮小字描述",
                    "display_code": "展示编码",
                    "display_type": "按钮展示类型",
                    "extra": {},
                    "hover_item": {},
                    "icon": "按钮图标",
                    "loading_config": {},
                    "name": "按钮名称",
                    "name_v2": {},
                    "show_question_icon": "是否展示小问号 （如上门取件不可用场景下，按钮名称旁边有个小问号icon）",
                    "style": "与前端ButtonItem对齐的样式",
                    "sub_button_list": [
                      {}
                    ],
                    "tag": "权益标签，如上门取件【我要寄件】按钮",
                    "tag_v2": {},
                    "tool_tip": "tip文案，如上门取件【我要寄件】按钮中气泡提示",
                    "tool_tip_v2": {},
                    "unread_count": "未读数"
                  },
                  "buttons": [
                    {}
                  ],
                  "detail_json": "展示详情信息字符串；如退券信息列表、红包信息列表",
                  "mark": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "text_list": "文案列表；例如卡券号列表",
                  "title": "弹窗主标题"
                },
                "fast_refund_half_screen_drawer": {
                  "button": {
                    "action": {},
                    "block": "是否允许点击",
                    "desc": "按钮小字描述",
                    "display_code": "展示编码",
                    "display_type": "按钮展示类型",
                    "extra": {},
                    "hover_item": {},
                    "icon": "按钮图标",
                    "loading_config": {},
                    "name": "按钮名称",
                    "name_v2": {},
                    "show_question_icon": "是否展示小问号 （如上门取件不可用场景下，按钮名称旁边有个小问号icon）",
                    "style": "与前端ButtonItem对齐的样式",
                    "sub_button_list": [
                      {}
                    ],
                    "tag": "权益标签，如上门取件【我要寄件】按钮",
                    "tag_v2": {},
                    "tool_tip": "tip文案，如上门取件【我要寄件】按钮中气泡提示",
                    "tool_tip_v2": {},
                    "unread_count": "未读数"
                  },
                  "button_list": [
                    {}
                  ],
                  "description": "描述",
                  "description_v2": [
                    {}
                  ],
                  "drawer_type": "标识场景类型比如 urge_pick_up",
                  "logo": {
                    "png": "png",
                    "webp": "webp"
                  },
                  "refund_progress_list": [
                    {}
                  ],
                  "tags": {},
                  "tips": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "title": "标题",
                  "title_v2": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  }
                },
                "focus_item": {
                  "fields_id": "聚焦组件id"
                },
                "freight_coupon_page": {
                  "descs": [
                    {}
                  ],
                  "max_compensate_amount_desc": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "notice": {
                    "icon": "icon",
                    "text": {}
                  },
                  "tag": "https://p9-piu.byteimg.com/tos-cn-i-8jisjyls3a/a5d94676e3e24a77aaa0c4a696a1fc9c~tplv-8jisjyls3a-3:0:0:q75.png",
                  "title": "弹窗主标题",
                  "valid_period_countdown": "倒计时文案"
                },
                "frequency_limit": "动画频控",
                "hal_screen_text_item": {
                  "card_items": [
                    {}
                  ],
                  "sub_title": "弹窗副标题",
                  "title": "弹窗主标题",
                  "total": {
                    "action": {},
                    "desc": {},
                    "full_line_text": {},
                    "side_click_icon": "点击图标，如小问号",
                    "side_sub_text": {},
                    "side_text": {},
                    "side_text_list": [
                      {}
                    ],
                    "tag": "文案旁的标签，eg:已赔付",
                    "text": "文案，eg:运费险"
                  }
                },
                "half_screen_drawer": {
                  "buttons": [
                    {}
                  ],
                  "desc": "弹窗说明文案",
                  "desc_v2": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "tags": {},
                  "title": "弹窗主标题"
                },
                "half_screen_drawer_v2": {
                  "backgroud_img": "backgroud_img",
                  "buttons": [
                    {}
                  ],
                  "logo": "logo",
                  "return_order_info": {
                    "actions": {},
                    "sku_img": "sku_img",
                    "sku_name": "sku_img",
                    "tips": {}
                  }
                },
                "json_data": "透传json数据",
                "json_name": "本次动作，json_data 解析后对应的 clickType，下划线格式 center_modal_item",
                "multi_drawer": {
                  "buttons": [
                    {}
                  ],
                  "deawer_item_inner_element": [
                    {}
                  ],
                  "title": "弹窗主标题"
                },
                "navigation": {
                  "from": {
                    "latitude": "纬度",
                    "longitude": "经度",
                    "name": "具体地址"
                  },
                  "to": {
                    "latitude": "纬度",
                    "longitude": "经度",
                    "name": "具体地址"
                  }
                },
                "persuade_cancel_info": {
                  "buttons": [
                    {}
                  ],
                  "desc": "弹窗说明文案",
                  "mail_address": {
                    "address": "地址",
                    "name": "姓名",
                    "phone": "电话"
                  },
                  "pick_up_time": "取件时间",
                  "station_info": {
                    "distance": "距离",
                    "location": "位置",
                    "operate_time": "营业时间",
                    "whole_name": "全名"
                  },
                  "title": "弹窗主标题"
                },
                "phone": {
                  "number": "电话号码"
                },
                "photo_popup_up_info": {
                  "buttons": [
                    {}
                  ],
                  "title": "弹窗主标题",
                  "url": "图片url"
                },
                "popup": {
                  "buttons": [
                    {}
                  ],
                  "desc": "弹窗说明文案",
                  "desc_v2": {
                    "text": "文案内容，其中高亮部分用 ${var_key} 表示",
                    "vars": {}
                  },
                  "rule_link": {
                    "schema": {},
                    "style": "与前端ButtonItem对齐的文案样式",
                    "text": "文案内容"
                  },
                  "tags": {},
                  "title": "弹窗主标题"
                },
                "refund_info_drawer": {
                  "account_point_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "allowance_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "coupon_info": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "credit_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "disable_red_pack_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "disable_supermarket_card_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "gold_coin_detail": {
                    "side_text": {},
                    "text": {}
                  },
                  "gold_coin_detail_v2": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "red_pack_info": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "refund_progress_list": [
                    {}
                  ],
                  "return_supermarket_card_detail": {
                    "card_list": [
                      {}
                    ],
                    "desc": {},
                    "desc_list": [
                      {}
                    ],
                    "elemtnt_detali_string": "券红包信息",
                    "link_text": {},
                    "promotion_type": "资产类型，用于区分element_detail_string的展示形式",
                    "side_text": {},
                    "sub_desc": {},
                    "text": "文案，eg:运费险"
                  },
                  "sub_desc": "分隔栏文案",
                  "sub_desc_for_disable": "作废区域文案",
                  "title": "弹窗主标题"
                },
                "refund_info_drawer_v2": {
                  "refund_progress_list": [
                    {}
                  ],
                  "resources_list": [
                    {}
                  ],
                  "title": "弹窗主标题"
                },
                "refund_recover": {
                  "recover_sdk_param": {},
                  "recover_type": "追缴类型，链接还是sdk",
                  "recover_url": "追缴链接",
                  "source_from": "追缴来源"
                },
                "schema": {
                  "replace": "跳转时是否关闭当前页面",
                  "toast_text": "跳转前toast提示文案",
                  "type": "跳转类型",
                  "value": "跳转类型"
                },
                "shipping_requirements_info": {
                  "buttons": [
                    {}
                  ],
                  "data": [
                    {}
                  ],
                  "title": "弹窗主标题"
                },
                "submit": {
                  "u_r_i": "指定请求地址"
                },
                "toast": {
                  "text": "toast内容"
                },
                "type": "点击动作类型",
                "type_select_drawer": {
                  "items": [
                    {}
                  ],
                  "title": "弹窗主标题",
                  "type": "类型（区分样式）"
                }
              },
              "blocked": "是否可点击",
              "button_guide_tip": {
                "detail": [
                  {}
                ]
              },
              "extra": {},
              "guide_msg": "提示信息",
              "hint": "额外提示",
              "hint_property": {
                "hint_position": "hint_position",
                "hint_type": "hint_type"
              },
              "i_d": "操作id",
              "icon": "按钮使用图标展示",
              "placeholder": {},
              "priority": "按钮优先级， 0最低，数字越大优先级越高，决定按钮在详情页的排列顺序",
              "related_i_d": "related_i_d",
              "style": "展示样式",
              "text": "展示文案",
              "url": "url"
            }
          ],
          "show_outside": "是否展示在文案外（APP侧使用，默认详情页小字文案是收起展示的）",
          "sub_text": "小字文案",
          "tags": [
            {
              "group": "标签从属(目前只有安心购)",
              "icon": "标签icon",
              "more_actions": [
                {
                  "action": {
                    "action_i_d": "特殊动作",
                    "apply_freight_info": {},
                    "batch_select_reason_drawer": {},
                    "combine_pop_up_item": {},
                    "compensate_drawer": {},
                    "confirm_exception_info": {},
                    "deduction_amount_info": {},
                    "drawer": {},
                    "fast_refund_half_screen_drawer": {},
                    "focus_item": {},
                    "freight_coupon_page": {},
                    "frequency_limit": "动画频控",
                    "hal_screen_text_item": {},
                    "half_screen_drawer": {},
                    "half_screen_drawer_v2": {},
                    "json_data": "透传json数据",
                    "json_name": "本次动作，json_data 解析后对应的 clickType，下划线格式 center_modal_item",
                    "multi_drawer": {},
                    "navigation": {},
                    "persuade_cancel_info": {},
                    "phone": {},
                    "photo_popup_up_info": {},
                    "popup": {},
                    "refund_info_drawer": {},
                    "refund_info_drawer_v2": {},
                    "refund_recover": {},
                    "schema": {},
                    "shipping_requirements_info": {},
                    "submit": {},
                    "toast": {},
                    "type": "点击动作类型",
                    "type_select_drawer": {}
                  },
                  "blocked": "是否可点击",
                  "button_guide_tip": {
                    "detail": [
                      {}
                    ]
                  },
                  "extra": {},
                  "guide_msg": "guide_msg",
                  "hint": "额外提示",
                  "hint_property": {
                    "hint_position": "hint_position",
                    "hint_type": "hint_type"
                  },
                  "i_d": "操作id",
                  "icon": "按钮使用图标展示",
                  "placeholder": {},
                  "priority": "按钮优先级， 0最低，数字越大优先级越高，决定按钮在详情页的排列顺序",
                  "related_i_d": "related_i_d",
                  "style": "展示样式",
                  "text": "展示文案",
                  "url": "url"
                }
              ],
              "more_info": {
                "evidence_list": "evidence_list",
                "info_type": "标签丰富信息类型枚举：after_sale_evidence：表示是凭证。",
                "title": "标签丰富信息的小标题。"
              },
              "placeholder": {},
              "position": "标签位置(title_left_top-列表页标题左上角)",
              "tag_detail": "服务标签名称",
              "tag_detail_en": "服务标签英文代号",
              "tag_detail_text": "服务标签详细文案",
              "tag_link_url": "服务跳转地址",
              "tag_type": "标签类型",
              "title": "标题",
              "url_name": "标签跳转文案/名称，APP使用"
            }
          ],
          "vars": {}
        },
        "status_code": "0",
        "status_msg": "success"
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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误，电话号码不合法"
}
```

## 备注
