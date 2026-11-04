# open.getOrderRecoveryRecommendation

> 一期暂无平台推荐策略能力，需三方自行制定。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.open.getOrderRecoveryRecommendation` |
| 中文名 | 一期暂无平台推荐策略能力，需三方自行制定 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/getOrderRecoveryRecommendation` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/8096 |
| 更新日期 | `2026-02-13` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `execute_condition` | body | string | 是 | 挽单执行时机：send_immediately 立即触发，send_after_sign 签收后触发，send_7_days_after_sign 签收后7天触发，send_after_evaluation 评价后触发 | `send_immediately` |
| `compensation_info` | body | array | 否 | 补偿信息 | `` |
| `  └ compensation_sub_type` | body | string | 否 | 补偿方式细分： 现金类：cash_small_payment 小额打款; cash_alipay 支付宝打款; cash_wechat 微信打款 实物商品类：physical_gift_item 赠品，如商品小样、周边等; physical_present 礼品 如额外采购、定制礼品 虚拟权益类：rights_coupon 优惠券；rights_private_point 私域积分；rights_extended_warranty 延保卡；rights_extended_trial 延长试用周期 | `cash_small_payment` |
| `  └ compensation_type` | body | string | 否 | 补偿方式：cash 现金类; physical 实物商品; rights 虚拟权益 | `cash` |
| `  └ compensation_name` | body | string | 否 | 若难以计算补偿金额，可填写名称（如：为消费者购买礼品的场景，可填写礼品名） | `玩偶` |
| `  └ extra` | body | string | 否 | 用于上报补偿方式扩展信息 | `{"extraInfo":"test"}` |
| `  └ compensation_amount` | body | number | 否 | 补偿权益金额，单位为分 | `1000` |
| `extra` | body | string | 否 | 用于上报挽单场景扩展信息 | `test` |
| `shop_order_id` | body | string | 是 | 订单号 | `123` |
| `after_sale_id` | body | string | 否 | 售后单号 | `123` |
| `recover_type` | body | string | 是 | 挽单类型：customer_service_human 人工客服; customer_service_robot 智能客服; sms 短信; outbound_call外呼; after_sales_tool售后工具 | `sms` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `can_recover` | boolean | 是否可挽 | `true` |
| `recover_trace_id` | string | 挽单ID，用于追踪全链路挽单动作 | `123456` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:10010） | 请检查上报接口穿传参 |
| `40004` | 非法的参数 / 订单与店铺不匹配（sub_code: isv.parameter-invalid:605090052） | 请检查订单ID |
| `40004` | 非法的参数 / 订单与售后单不匹配（sub_code: isv.parameter-invalid:605090053） | 请检查订单与售后单ID |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:10010",
  "sub_msg": "参数非法"
}
```

## 备注
