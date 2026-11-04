# 合单校验

> order.mergeV2 — 合单校验接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 合单校验 |
| 文档地址 | `/docs/doudian/order/order-order-mergeV2` |
| 接口 ID | `doudian.order.order.mergeV2` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/mergeV2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/6649 |
| 更新日期 | `2024-06-21` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `merge_list` | body | array | 否 | 合单列表 | `` |
| `  └ order_id` | body | string | 否 | 店铺单id | `123123` |
| `  └ open_address_id` | body | string | 否 | open address id | `xxxxxxxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolProductShare?app_key=your_appkey_here&method=buyin.kolProductShare&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_list` | array | 合单结果。可合单的订单ID列表用逗号分隔的字符串表示。比如，1111,2222表示订单1111和订单2222可合并发货。 | `['123123','4564566']` |
| `failed_order` | string | key是失败订单id，value是失败原因 | `<"111":"订单不在发货状态">` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `80000` | 风控拦截 / 存在安全风险（sub_code: isv.risk-control-failed:300011） | 请稍后重试 |
| `50002` | 业务处理失败 / 200101:查询订单失败（sub_code: isv.business-failed:200101） | 200101:查询订单失败 |
| `50002` | 业务处理失败 / 100000:订单重复：6936337193395099095（sub_code: isv.business-failed:100000） | 100000:订单重复：6936337193395099095 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "coupon_link": {
        "coupon_status": "0",
        "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674",
        "qrcode": {
          "height": "360",
          "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
          "width": "360"
        },
        "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη",
        "share_link": "https://alliance.jinritemai.com"
      },
      "dy_deeplink": "nssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927&so",
      "dy_password": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη",
      "dy_zlink": "https://z.douyin.com/xxxxxxx",
      "qr_code": {
        "height": "360",
        "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
        "width": "360"
      },
      "share_link": "https://haohuo.jinritemai.YOUR_SECRET_KEY.html?id=",
      "use_ins_activity": "0"
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
  "code": 80000,
  "msg": "风控拦截",
  "sub_code": "isv.risk-control-failed:300011",
  "sub_msg": "存在安全风险"
}
```

## 备注
