# 营销中心-创建优惠券

> marketing.createCoupon — 营销中心-创建优惠券

| 元信息 | 值 |
| --- | --- |
| 中文名 | 营销中心-创建优惠券 |
| 文档地址 | `/docs/doudian/shop/shop-marketing-createCoupon` |
| 接口 ID | `doudian.shop.marketing.createCoupon` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/createCoupon` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/523 |
| 更新日期 | `2024-06-11` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_name` | body | string | 是 | 优惠券名称 | `优惠券名称` |
| `type` | body | mixed | 是 | 优惠券类型,21 商家折扣券 22 商家直减券 23 商家满减券 31 渠道折扣券 32 渠道直减券 33 渠道满减券 41 单品折扣券 42 单品直减券 43 单品满减券 | `21` |
| `period_type` | body | mixed | 是 | 有效期类型,1固定有效期类型，2浮动有效期类型 | `1` |
| `valid_period` | body | mixed | 是 | 如果period_type = 2 浮动有效期（单位：天） | `2` |
| `start_apply_time` | body | string | 是 | 开始领取时间,格式2006-01-02 15:04:05 | `2006-01-02 15:04:05` |
| `end_apply_time` | body | string | 是 | 结束领取时间 | `2006-01-03 15:04:05` |
| `start_time` | body | string | 是 | 开始生效时间 | `2006-01-02 15:04:05` |
| `expire_time` | body | string | 是 | 结束生效时间 | `2006-01-03 15:04:05` |
| `total_amount` | body | mixed | 是 | 总数量 | `111` |
| `type_detail` | body | string | 否 | 根据type传不同参数,商家券shop_id,商品券->多个商品id | `0` |
| `discount` | body | mixed | 是 | 折扣券折扣，8.5折传85 | `85` |
| `max_discount_limit` | body | mixed | 是 | 折扣最高抵扣金额 分 | `0` |
| `threshold` | body | mixed | 是 | 满减券门槛 分 | `1000` |
| `credit` | body | mixed | 是 | 满减券，直减券金额 分 | `200` |
| `max_apply_times` | body | mixed | 是 | 最大领取次数限制 | `1` |
| `url` | body | string | 是 | url | `url` |
| `op_name` | body | string | 是 | 店铺名 | `店铺名` |
| `is_show` | body | mixed | 是 | 0 全网店铺推广  1自有渠道 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/createCoupon?app_key=your_appkey_here&method=marketing.createCoupon&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `coupon_meta_id` | mixed | 优惠券ID | `优惠券ID` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "coupon_meta_id": "优惠券ID"
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
