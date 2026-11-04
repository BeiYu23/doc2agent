# member.getShopShortLink

> 获取商家推广链接接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.member.getShopShortLink` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/getShopShortLink` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1455 |
| 更新日期 | `2026-05-12` |

## 接口说明

- 文档书: 店铺API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `link_type` | body | mixed | 是 | 链接类型（1-会员中心，2-达人主页，3-店铺首页, 4-商品详情页，5-订单详情页，6-优惠券领取, 7-店铺七分屏 8-直播间） | `1` |
| `product_id` | body | string | 否 | 商品id，生成商品详情页链接需要 | `123456` |
| `order_id` | body | string | 否 | 订单id，生成订单详情页链接需要 | `123456` |
| `coupon_meta_id` | body | string | 否 | 优惠券id，生成领取优惠券链接需要 | `123456` |
| `aweme_uid` | body | string | 否 | 抖音号（仅当linkType为8时选填） | `PROYA_STORE` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/getShopShortLink?app_key=your_appkey_here&method=member.getShopShortLink&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `short_link` | string | 对应类型的链接，有效时间60天，长度21~24 | `z.douyin.com/9xNklYc` |
| `link_id` | mixed | 短链唯一链接id | `7402147984902783282` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 当前店铺未开通会员服务（sub_code: isv.business-failed:-300002） | 检查类型参数，未开通店铺会员的商家无会员中心链接 |
| `20000` | 系统错误 / 服务器开小差了，请稍后重试（sub_code: isp.service-error:-500） | 请稍后重试 |
| `50002` | 业务处理失败 / 网络错误，请稍后重试（sub_code: isv.business-failed:628145000） | 请稍后重试 |
| `40004` | 非法的参数 / 抖音号错误（sub_code: isv.parameter-invalid:628002001） | 确认输入的抖音号 |

## 响应示例

成功：

```json
{
  "data": {
    "link_id": "7402147984902783282",
    "short_link": "z.douyin.com/9xNklYc"
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
  "sub_code": "isv.business-failed:-300002",
  "sub_msg": "当前店铺未开通会员服务"
}
```

## 备注
