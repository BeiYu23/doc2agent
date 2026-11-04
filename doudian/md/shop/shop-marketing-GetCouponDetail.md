# 优惠券详细信息查询

> marketing.GetCouponDetail — 优惠券详细信息查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 优惠券详细信息查询 |
| 文档地址 | `/docs/doudian/shop/shop-marketing-GetCouponDetail` |
| 接口 ID | `doudian.shop.marketing.GetCouponDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/GetCouponDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/518 |
| 更新日期 | `2024-07-17` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_meta_id` | body | mixed | 否 | 优惠券ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/GetCouponDetail?app_key=your_appkey_here&method=marketing.GetCouponDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `coupon_meta` | object | 优惠券 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "coupon_meta": {
      "coupon_meta_id": "123",
      "coupon_name": "券的名称",
      "coupon_string": "券标签文案",
      "credit": "10",
      "end_apply_time": "2021-05-06 15:04:05",
      "expire_time": "2021-05-06 15:04:05",
      "is_show": "1",
      "left_amount": "1",
      "max_apply_times": "1",
      "max_discount_limit": "1",
      "pay_type": "1",
      "period_type": "1",
      "shop_id": "1111",
      "shop_logo": "1",
      "shop_name": "店铺名称",
      "start_apply_time": "2021-05-06 15:04:05",
      "start_time": "2021-05-06 15:04:05",
      "status": "1",
      "threshold": "10",
      "total_amount": "11",
      "type": "21",
      "type_detail": "指定店铺/商品id集合",
      "type_string": "券限制描述文案",
      "url": "https://www.xxx.xxx",
      "used_amount": "1",
      "user_apply_times": "10",
      "valid_period": "1",
      "what_coupon": "券类型文案"
    }
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
