# 批量获取优惠券信息

> max.coupons — 批量获取优惠券信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量获取优惠券信息 |
| 文档地址 | `/docs/doudian/shop/shop-max-coupons` |
| 接口 ID | `doudian.shop.max.coupons` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/max/coupons` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2833 |
| 更新日期 | `2025-09-22` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_meta_ids` | body | array | 否 | 优惠券id列表，手动配置的时候传 | `111,222` |
| `m_config_type` | body | mixed | 是 | 配置类型 0 手动配置，1 智能配置，默认手动配置 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/max/coupons?app_key=your_appkey_here&method=max.coupons&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `coupons` | array | 优惠券数组 | `` |
| `status_code` | mixed | 状态码 | `0` |
| `status_msg` | string | 状态说明 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 啊哦，服务器打瞌睡了，再试一次吧～（sub_code: isp.service-error:4） | 再试一次 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "coupons": [
      {
        "action_type": "1",
        "action_value": "sslocal://goods/store?sec_shop_id=blccms",
        "apply_status": "1",
        "apply_toast": "本店全店可用，下单即享优惠",
        "coupon_biz_type": "7",
        "coupon_meta_id": "1111",
        "coupon_range": "aa",
        "credit": "1000",
        "discount": "0.8",
        "discount_limit": "1",
        "expire_time": "0",
        "is_discount": "false",
        "is_show": "0",
        "period_display": "2006-01-02 15:04:05-2006-01-03 15:04:05",
        "period_type": "1",
        "start_time": "0",
        "status_text": "领取",
        "tags": "通用券",
        "threshold": "10000",
        "threshold_text": "满100可用",
        "time_limit": "领用当日起2天内有效",
        "type": "22",
        "valid_period": "2",
        "what_coupon": "店铺券"
      }
    ],
    "status_code": "0",
    "status_msg": "success"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:4",
  "sub_msg": "啊哦，服务器打瞌睡了，再试一次吧～"
}
```

## 备注
