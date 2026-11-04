# marketing.couponDigest

> 查询优惠券摘要信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.marketing.couponDigest` |
| 中文名 | 查询优惠券摘要信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/couponDigest` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7518 |
| 更新日期 | `2025-06-16` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_id` | body | mixed | 否 | 优惠券id | `7514258635758387491` |
| `coupon_shop_id` | body | mixed | 否 | 店铺id | `4463798` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/couponDigest?app_key=your_appkey_here&method=marketing.couponDigest&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `coupon_meta` | object | 优惠券信息 | `` |

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
      "coupon_name": "商品优惠券 20250610",
      "coupon_string": "满10减2券",
      "credit": "10",
      "end_apply_time": "2021-05-06 15:04:05",
      "expire_time": "2021-05-06 15:04:05",
      "is_show": "1",
      "left_amount": "1",
      "max_apply_times": "1",
      "max_discount_limit": "1",
      "pay_type": "1",
      "period_type": "1",
      "start_apply_time": "2021-05-06 15:04:05",
      "start_time": "2021-05-06 15:04:05",
      "status": "1",
      "threshold": "10",
      "total_amount": "11",
      "type": "21",
      "type_detail": "\"3754891696425533894,3757071684562190510,3757107107304964475,3757107203866231129,3757107465859236084,3757107474449170737\"",
      "type_string": "店铺指定商品可用",
      "used_amount": "1",
      "user_apply_times": "1",
      "valid_period": "1",
      "what_coupon": "店铺商品券"
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
