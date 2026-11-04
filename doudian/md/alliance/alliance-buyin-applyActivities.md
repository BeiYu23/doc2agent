# buyin.applyActivities

> 商品团长活动提报接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.applyActivities` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/applyActivities` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/744 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V7.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 是 | 团长活动ID | `1234234123` |
| `service_rate` | body | mixed | 否 | 招商服务费率。 服务费率+佣金率小于90（废弃） | `20` |
| `phone_number` | body | string | 是 | 店铺联系电话 | `12318726321` |
| `products` | body | array | 是 | 商品列表 | `` |
| `  └ promotion_end_time` | body | string | 否 | 商品推广结束时间（不传默认为当前时间往后数90天） | `2022-02-11` |
| `  └ gift_info` | body | string | 否 | 赠品（15个字以内，填写可提供赠品详情） | `无赠品` |
| `  └ product_ad_activity_ratio` | body | string | 否 | 双佣金投放期佣金比例（小数）,这里传字符串是为了便于比较小数位数 | `20.5` |
| `  └ product_id` | body | mixed | 是 | 商品ID | `12312313123` |
| `  └ commission_rate` | body | mixed | 否 | 佣金比例，设置范围[1%,50%]不小于改团长活动设置佣金率（废弃） | `20` |
| `  └ promotion_stock` | body | mixed | 否 | 参与活动库存 | `100` |
| `  └ promotion_step` | body | string | 否 | 活动价实现方式（15个字以内，如满减、提供优惠券、拍立减、限时活动价） | `满减` |
| `  └ product_activity_ratio` | body | string | 否 | 佣金比例，设置范围[0,80%]，并且不能不小于该团长活动设置佣金率（必须为两位小数） | `20.50` |
| `  └ months_of_protection` | body | mixed | 否 | 开启独家保护的时长。单位：月；范围：[0,12]，0表示不开启 | `1` |
| `  └ activity_price` | body | mixed | 是 | 活动价（单位分） | `200` |
| `service_ratio` | body | string | 否 | 招商服务费率。 服务费率+佣金率小于90（必须为两位小数） | `20.50` |
| `cos_type` | body | mixed | 否 | 佣金类型 0:固定佣金 1:双佣金 | `1` |
| `ad_service_ratio` | body | string | 否 | 双佣金投放期服务费率（小数） | `15.0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/applyActivities?app_key=your_appkey_here&method=buyin.applyActivities&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 操作的商品数量 | `20` |
| `result` | array | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 活动报名时间已结束，不支持继续报名（sub_code: isv.business-failed:110110） | 活动报名时间已结束，不支持继续报名 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:500） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 小数服务费率不合法，必须为两位小数（sub_code: isv.business-failed:8192） | 小数服务费率不合法，必须为两位小数 |
| `50002` | 业务处理失败 / 请检查输入参数（sub_code: isv.business-failed:10001） | 请检查输入参数 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "error_code": "0",
        "error_msg": "success",
        "is_success": "true",
        "product_id": "123123123123"
      }
    ],
    "total": "20"
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
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
