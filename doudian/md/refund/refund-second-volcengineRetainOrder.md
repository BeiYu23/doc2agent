# second.volcengineRetainOrder

> 核心入口，用于对单一退货的订单进行全面评估

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.second.volcengineRetainOrder` |
| 中文名 | 核心入口，用于对单一退货的订单进行全面评估 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/volcengineRetainOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/8135 |
| 更新日期 | `2026-05-08` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 否 | 店铺退货的订单ID | `123456789012345` |
| `shop_config` | body | object | 否 | 商家自定义配置 | `` |
| `  └ roi_threshold` | body | string | 否 | 商家期望的最小ROI | `1.2` |
| `  └ profit_rate` | body | string | 否 | 自定义毛利率 | `0.45` |
| `  └ supported_benefits` | body | array | 否 | 商家支持的挽单权益，用于策略模型挑选最合适的权益类型 | `` |
| `    └ type` | body | string | 否 | 权益类型，枚举值为： - coupon：优惠券（高面额低成本） - gift：礼品/小样（利用高感知价值/低成本的价格差，以小博大） - cash：现金红包（直接有效，适合低客单价商品） - partial_refund：订单部分退款（无需额外营销预算，走售后逆向流程） | `coupon` |
| `    └ cash_range` | body | array | 否 | 现金红包范围，如：[1, 10]，1元到10元 若type=cash，则必填 | `[1.0. 10.0]` |
| `    └ gift_sku_id` | body | mixed | 否 | 小样SKu ID | `12222` |
| `    └ gift_market_value` | body | string | 否 | 礼品/小样的市场价格 若type=gift必填 | `89.0` |
| `    └ refund_amount` | body | string | 否 | 退款金额上限 type=partial_refund必填 | `50.0` |
| `    └ coupon_face_value` | body | string | 否 | 券面额， 如20 若type=coupon必填 | `5.0` |
| `    └ coupon_threshold` | body | string | 否 | 优惠券使用门槛金额 (0 代表无门槛)，如100 若type=coupon必填 | `100.0` |
| `    └ refund_ratio` | body | string | 否 | 订单金额退款比例 type=partial_refund必填 | `0.3` |
| `    └ benefit_id` | body | string | 否 | 权益ID，唯一标识当前商家配置的权益，若有的话，可以选择传递过来 | `123` |
| `    └ gift_cost` | body | string | 否 | 礼品/小样的实际成本 若type=gift必填 | `15.0` |
| `    └ name` | body | string | 否 | 权益名称，如：type=gift，name=SK-II神仙水小样(10ml) type=coupon，name=满100减10券 | `SK-II神仙水小样(10ml)` |
| `after_sale_id` | body | string | 否 | 售后单ID | `123456789012345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/volcengineRetainOrder?app_key=your_appkey_here&method=second.volcengineRetainOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `wool_prob` | string | 薅羊毛概率 (0.0 - 1.0) | `0.12` |
| `strategy` | object | 权益建议，若商家入参配置了权益列表，策略引擎会从中选出最优的选项并返回 否则，会按照策略引擎自己的理解返回建议 | `` |
| `is_hit_strategy` | string | 是否命中策略，用于做A/B实验 “0”: 未命中，下方字段返回默认值，不要使用 “1”：命中，可使用下方数据用于挽单决策 | `1` |
| `retention_prob` | string | 挽回概率 (0.0 - 1.0) | `0.7` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不对，请检查（sub_code: isv.parameter-invalid:40001） | 缺少必要的参数或订单号不存在，请检查 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:50201） | 请反馈平台开发 |
| `20001` | 内部服务超时 / 业务请求超时（sub_code: isp.service-timeout-error:50401） | 业务请求超时，请重试 |
| `20000` | 系统错误 / 业务处理失败（sub_code: isp.service-error:50000） | 请反馈平台开发 |

## 响应示例

成功：

```json
{
  "data": {
    "is_hit_strategy": "1",
    "retention_prob": "0.7",
    "strategy": {
      "benefit": {
        "benefit_id": "123",
        "condition": "on_receipt",
        "display_name": "满100减10券",
        "name": "SK-II神仙水小样(10ml)",
        "type": "coupon",
        "value": "SK-II神仙水小样(10ml)"
      },
      "touch": {
        "scheduled_time": "[\"10:00-12:00\",  \"14:00-14:30\"]",
        "timing": "scheduled"
      }
    },
    "wool_prob": "0.12"
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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "参数不对，请检查"
}
```

## 备注
