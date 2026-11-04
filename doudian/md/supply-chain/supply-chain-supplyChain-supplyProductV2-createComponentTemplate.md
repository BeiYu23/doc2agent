# supplyChain.supplyProductV2.createComponentTemplate

> 创建尺码模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.createComponentTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6673 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_type` | body | string | 否 | 模板类型: size_info(尺码表) | `` |
| `template_sub_type` | body | string | 否 | 指定模板类型: clothing、undies、shoes、children_clothing | `` |
| `template_name` | body | string | 否 | 模板名称 | `` |
| `component_front_data` | body | string | 否 | 商品组件数据 json | `` |
| `shareable` | body | boolean | 否 | 是否可共享 0：是 1：否 | `` |
| `category_id` | body | mixed | 否 | 类目id，用来确定模板类型 | `` |
| `only_check` | body | boolean | 否 |  | `` |
| `is_commit` | body | boolean | 否 | 是否是草稿提交 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/getShopAccountItem?app_key=your_appkey_here&method=order.getShopAccountItem&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 返回code | `100` |
| `msg` | string | 返回msg | `“”` |
| `success` | boolean | 是否成功 | `true` |
| `template_id` | mixed | 模版id | `111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[CreateComponentTemplateV2] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110250112] BizStatusMessage:[选中的尺码数量和表格行数量不一致]}（sub_code: isv.business-failed:2000） | 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[CreateComponentTemplateV2] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110250112] BizStatusMessage:[选中的尺码数量和表格行数量不一致]} |
| `50002` | 业务处理失败 / 1020:参数异常，请检查后重试\|供应商信息异常（sub_code: isv.business-failed:1020） | 1020:参数异常，请检查后重试\|供应商信息异常 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "10000",
    "code_msg": "SUCCESS",
    "data": [
      {
        "account_amount": "96",
        "account_bill_desc": "订单结算",
        "account_bill_desc_tag": "3",
        "account_trade_no": "AS202110050707321602785799467_IN",
        "account_type": "1",
        "account_type_desc": "微信",
        "actual_zr_pay_promotion": "0",
        "actual_zt_pay_promotion": "0",
        "after_sale_service_no": "SS7015036721667375372",
        "author_coupon_subsidy": "0",
        "author_id": "123123123",
        "author_name": "达人名称示例",
        "bank_pay_promotion_amount": "0",
        "bill_time": "2021-10-01 10:10:11",
        "biz_type": "1",
        "biz_type_desc": "鲁班广告",
        "business_order_create_time": "2021-09-26 20:46:16",
        "channel_fee": "0",
        "channel_promotion_fee": "0",
        "colonel_service_fee": "0",
        "commission": "-1",
        "free_commission_flag": "是",
        "fund_flow": "1",
        "fund_flow_desc": "出账",
        "gov_promotion_amount": "0",
        "order_id": "4847151209529677080",
        "order_type": "0",
        "order_type_desc": "普通订单",
        "other_sharing_amount": "0",
        "partner_commission": "0",
        "pay_amount": "100",
        "platform_service_fee": "-3",
        "post_amount": "0",
        "post_promotion_amount": "0",
        "product_id": "3494738440426276563",
        "product_name": "商品名称示例",
        "promotion_amount": "0",
        "real_free_commission_amount": "0",
        "recycler_amount": "0",
        "refund_amount": "0",
        "remark": "无",
        "shop_id": "12344",
        "shop_order_id": "4847151209529677080",
        "trans_scene": "消费者赔付",
        "trans_scene_tag": "1"
      }
    ],
    "data_size": "100",
    "is_end": "1",
    "next_start_index": "d746da31eee45e65d07b20f87d6844bbf72041350acc66af1711408070b62428",
    "next_start_time": "2021-10-01 06:00:00",
    "size": "100"
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
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "2000:业务处理异常|RPCError{PSM:[cmp.ecom.product_backend] Method:[CreateComponentTemplateV2] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110250112] BizStatusMessage:[选中的尺码数量和表格行数量不一致]}"
}
```

## 备注
