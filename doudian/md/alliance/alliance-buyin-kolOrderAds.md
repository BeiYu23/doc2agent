# 查询达人的直播间分销、商品分销、活动页分销订单

> buyin.kolOrderAds — 查询达人的直播间分销、商品分销、活动页分销订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询达人的直播间分销、商品分销、活动页分销订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-kolOrderAds` |
| 接口 ID | `doudian.alliance.buyin.kolOrderAds` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/kolOrderAds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/5489 |
| 更新日期 | `2023-10-31` |

## 接口说明

- 文档书: 精选联盟API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 每页订单数目，取值区间： [1, 20] | `20` |
| `cursor` | body | string | 否 | 下一页索引（第一页传“0”） | `0` |
| `start_time` | body | string | 否 | 支付时间开始，最早支持2021年10月01日 | `2006-01-02 15:04:05` |
| `end_time` | body | string | 否 | 支付时间结束，该时间不能超过start_time+90 | `2006-01-02 15:04:05` |
| `order_ids` | body | string | 否 | 订单号。多个订单号用英文 , 分隔，最多支持10个订单号 | `4737996432465788974,4737996432465780075` |
| `pid` | body | string | 否 | PID | `dy_1234_4567_789` |
| `distribution_type` | body | string | 否 | Live-直播间，ProductDetail-商品详情，Activity-活动（百亿补贴/秒杀）Mix-H5自建活动页 | `Live` |
| `open_id` | body | string | 否 | 用户抖店open_id | `dsrr34fd43fe` |
| `time_type` | body | string | 否 | 查询时间类型。pay: 支付时间（默认）; update：联盟侧更新时间，非订单状态更新时间 | `update` |
| `query_order_type` | body | number | 否 | 不填或者填0：查询分销订单，1：查询比价订单 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolOrderAds?app_key=your_appkey_here&method=buyin.kolOrderAds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 获取用户客户端账户信息失败（sub_code: isv.business-failed:4158） | 获取用户客户端账户信息失败 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 无效size |
| `40004` | 非法的参数 / 无效order_ids（sub_code: isv.parameter-invalid:1032） | 无效order_ids |
| `40004` | 非法的参数 / 请指定时间范围或订单号（sub_code: isv.parameter-invalid:1033） | 请指定时间范围或订单号 |
| `40004` | 非法的参数 / 无效开始时间（sub_code: isv.parameter-invalid:1034） | 无效开始时间 |
| `40004` | 非法的参数 / 无效结束时间（sub_code: isv.parameter-invalid:1035） | 无效结束时间 |
| `40004` | 非法的参数 / 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:1036） | 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `40004` | 非法的参数 / 无效 PID（sub_code: isv.parameter-invalid:1039） | 无效 PID |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 256:服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 起始查询时间超过了最久查询限制（sub_code: isv.parameter-invalid:4168） | 起始查询时间超过了最久查询限制 |
| `50002` | 业务处理失败 / 无效订单查询时间类型（sub_code: isv.business-failed:282） | 无效订单查询时间类型 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:4497） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "cursor": "4737996432465788974",
      "orders": [
        {
          "ads_activity_id": "1001",
          "ads_estimated_commission": "100",
          "ads_estimated_tech_service_fee": "1000",
          "ads_fans_type": "old",
          "ads_promotion_rate": "10",
          "ads_real_commission": "100",
          "ads_split_rate": "0",
          "app": "抖音",
          "author_account": "我的昵称",
          "author_buyin_id": "123467",
          "author_openid": "f190e172-5fd8-4b7b-babb-f32323e60f7b",
          "author_short_id": "kodofo",
          "buyer_openid": "f190e172-5fd8-4b7b-babb-f32323e60f7b",
          "commission_rate": "2000",
          "estimated_commission": "165",
          "estimated_tech_service_fee": "12",
          "estimated_total_commission": "2",
          "flow_point": "PAY_SUCC",
          "item_num": "2",
          "live_ads_type": "Self",
          "media_type": "shop_list",
          "order_id": "4737996432465788974",
          "pay_goods_amount": "1100",
          "pay_success_time": "2006-01-02 15:04:05",
          "pick_source_client_key": "jifji32rnu3jit43",
          "pid_info": {
            "external_info": "1222_2333",
            "media_type_name": "Live",
            "pid": "dy_1234_33_455"
          },
          "product_activity_id": "1",
          "product_id": "3450632721376902816",
          "product_img": "https://tosv.boe.byted.org/obj/temai/7e92a281163e33cedef99d8735d1e90bwww828-708",
          "product_name": "测试商品",
          "real_commission": "165",
          "refund_time": "2006-01-02 15:04:05",
          "settle_time": "2006-01-02 15:04:05",
          "settled_goods_amount": "0",
          "settled_tech_service_fee": "12",
          "shop_estimated_commission": "12",
          "shop_id": "1234",
          "shop_name": "我的店铺",
          "shop_real_commission": "12",
          "total_pay_amount": "2100",
          "update_time": "2006-01-02 15:04:05"
        }
      ]
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
