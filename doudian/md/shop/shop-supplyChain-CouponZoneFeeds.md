# supplyChain.CouponZoneFeeds

> 二级承接页初始化

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.supplyChain.CouponZoneFeeds` |
| 中文名 | 二级承接页初始化 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/CouponZoneFeeds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2854 |
| 更新日期 | `2023-03-09` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_meta_id` | body | string | 是 | 优惠券id | `7173718548748321035` |
| `scene` | body | string | 是 | 场景，根据时新客还是老客，调用不同的Feed策略。1-新客 2-老客 | `1` |
| `enter_time` | body | string | 是 | 进入页面的时间，单位：秒 | `16721287591` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/CouponZoneFeeds?app_key=your_appkey_here&method=supplyChain.CouponZoneFeeds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tab_list` | array | tab列表 | `` |
| `coupon_info` | object | 优惠券信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 网络错误，请稍后重试（sub_code: isp.service-error:300） | 网络错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "coupon_info": {
      "apply_token": "164b615fef5d56f453e7b80c32e23990e02d003dd65d9e30db7d4541d95baec5",
      "coupon_apply_status": "1",
      "coupon_meta_id": "7173718548748321036",
      "credit": "400",
      "expire_time": "1675180799",
      "start_time": "1675094400",
      "status": "2",
      "threshold": "4000"
    },
    "tab_list": [
      {
        "goods_feed": {
          "cursor": "1",
          "feed_end": "false",
          "goods_cards": [
            {
              "detail_url": "略",
              "img_url": "略",
              "is_activity_price": "false",
              "is_live_product": "true",
              "product_id": "略",
              "promotion_id": "略",
              "promotion_source": "1",
              "sell_num": "123",
              "show_hot_sell_tag": "true",
              "show_new_user_tag": "true",
              "show_price": "123",
              "tags": "略",
              "title": "略"
            }
          ]
        },
        "is_tab_name_show": "true",
        "tab_code": "1",
        "tab_name": "100元好物"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:300",
  "sub_msg": "网络错误，请稍后重试"
}
```

## 备注
