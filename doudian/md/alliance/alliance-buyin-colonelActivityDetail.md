# buyin.colonelActivityDetail

> 获取团长活动详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.colonelActivityDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonelActivityDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1670 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 是 | 活动ID | `54321` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/colonelActivityDetail?app_key=your_appkey_here&method=buyin.colonelActivityDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `institution_id` | mixed | 机构ID | `794156847175` |
| `activity_id` | mixed | 活动ID | `54321` |
| `is_new_shop` | boolean | 报名门槛是否限制新手店铺 | `true` |
| `shop_type` | array | 报名门槛。0：普通店；1：专营店；2：旗舰店；3：专卖店；4：商场店；5:专卖型旗舰店；6:官方旗舰店；7:企业店；8:个体店 | `0` |
| `activity_name` | string | 活动名称 | `一个活动` |
| `activity_desc` | string | 活动描述 | `一个活动` |
| `apply_start_time` | string | 活动报名开始时间 | `2022-01-10` |
| `apply_end_time` | string | 活动报名结束时间 | `2022-02-20` |
| `commission_rate` | string | 活动要求的最低佣金率 | `500` |
| `service_rate` | string | 活动要求的最低服务费率 | `1000` |
| `wechat_id` | string | 微信号（返回微信号密文，需通过 https://op.jinritemai.com/docs/api-docs/61/2829 解密） | `6UNGOWt5MkBIgEDQ1I31w==` |
| `phone_num` | string | 手机号（返回联系电话密文，需通过 https://op.jinritemai.com/docs/api-docs/61/2829 解密） | `6UNGOWt5MkBIgEDQ1I31w==` |
| `estimated_single_sale` | string | 预估销售额 | `1000` |
| `activity_type` | mixed | 活动类型。1： 全部商家； 2： 指定商家 | `1` |
| `specified_shop_ids` | string | 指定商家ID | `0` |
| `categories` | array | 招商类目 | `1` |
| `shop_score` | mixed | 报名门槛-店铺体验分选项。0表示不限 | `0` |
| `min_promotion_days` | mixed | 最短推广周期，0：不限；>0:具体天数；现在只有0、15、30、60、90 | `15` |
| `threshold_cross_border` | mixed | 跨境店铺 可/不可 报名（0:跨境店铺可报名，1:跨境店铺不可报名） | `0` |
| `has_threshold` | boolean | 是否有报名门槛 | `true` |
| `colonel_buyin_id` | mixed | 团长百应ID | `1467231562381423` |
| `months_of_protection` | mixed | 团长活动设置的限时独家期限 0-6个月, 单位：月 | `1` |
| `colonel_name` | string | 团长名称 | `一个团长` |
| `cos_limit_type` | mixed | 佣金限制类型1:不限制 2:仅双佣金 3:仅固定佣金 | `1` |
| `ad_commission_rate` | string | 最低双佣金投放期商品佣金率 | `1000` |
| `ad_service_rate` | string | 最低双佣金投放期服务费率 | `500` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 活动不存在（sub_code: isv.business-failed:500） | 活动不存在 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_desc": "一个活动",
    "activity_id": "54321",
    "activity_name": "一个活动",
    "activity_type": "1",
    "ad_commission_rate": "1000",
    "ad_service_rate": "500",
    "apply_end_time": "2022-02-20",
    "apply_start_time": "2022-01-10",
    "categories": "1",
    "colonel_buyin_id": "1467231562381423",
    "colonel_name": "一个团长",
    "commission_rate": "500",
    "cos_limit_type": "1",
    "estimated_single_sale": "1000",
    "has_threshold": "true",
    "institution_id": "794156847175",
    "is_new_shop": "true",
    "min_promotion_days": "15",
    "months_of_protection": "1",
    "phone_num": "6UNGOWt5MkBIgEDQ1I31w==",
    "service_rate": "1000",
    "shop_score": "0",
    "shop_type": "0",
    "specified_shop_ids": "0",
    "threshold_cross_border": "0",
    "wechat_id": "6UNGOWt5MkBIgEDQ1I31w=="
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
  "sub_code": "isv.business-failed:500",
  "sub_msg": "活动不存在"
}
```

## 备注
