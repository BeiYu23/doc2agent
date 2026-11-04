# 团长分次结算订单

> buyin.colonelMultiSettlementOrders — 团长分次结算订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 团长分次结算订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-colonelMultiSettlementOrders` |
| 接口 ID | `doudian.alliance.buyin.colonelMultiSettlementOrders` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonelMultiSettlementOrders` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2704 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 每页订单记录数目，最大100 | `50` |
| `cursor` | body | string | 否 | 下一页索引，默认传‘0’ | `0` |
| `time_type` | body | string | 否 | 查询时间类型。settle: 结算时间）; update：更新时间（默认) | `update` |
| `start_time` | body | string | 否 | 开始时间 | `2022-10-01 15:04:05` |
| `end_time` | body | string | 否 | 结束时间， 开始与结束时间最大时间间隔为90天 | `2022-10-31 15:04:05` |
| `order_ids` | body | string | 否 | 订单号列表，','分隔，最多100个 | `4737996432465788974,4737996432465788973` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/colonelMultiSettlementOrders?app_key=your_appkey_here&method=buyin.colonelMultiSettlementOrders&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 无效size |
| `40004` | 非法的参数 / 无效订单查询时间类型（sub_code: isv.parameter-invalid:282） | 无效订单查询时间类型 |
| `40004` | 非法的参数 / 无效order_ids（sub_code: isv.parameter-invalid:1032） | 无效order_ids |
| `40004` | 非法的参数 / 请指定时间范围或订单号（sub_code: isv.parameter-invalid:1033） | 请指定时间范围或订单号 |
| `40004` | 非法的参数 / 无效开始时间（sub_code: isv.parameter-invalid:1034） | 无效开始时间 |
| `40004` | 非法的参数 / 无效结束时间（sub_code: isv.parameter-invalid:1035） | 无效结束时间 |
| `40004` | 非法的参数 / 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d）（sub_code: isv.parameter-invalid:1036） | 无效时间区间（开始时间不能大于结束时间，并且不能小于t-90d） |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 无效cursor（sub_code: isv.parameter-invalid:284） | 无效cursor |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "cursor": "98777",
      "orders": [
        {
          "ads_buyin_id": "79989901209",
          "author_account": "作者账号",
          "author_buyin_id": "79989901209",
          "colonel_activity_id": "302931",
          "colonel_buyin_id": "78790909302931",
          "colonel_institution_name": "我是团长",
          "order_id": "4737996432465788974",
          "phase_id": "3",
          "product_id": "3450632721376902816",
          "product_name": "测试商品1",
          "second_colonel_activity_id": "31929",
          "second_colonel_buyin_id": "7888989892133",
          "second_colonel_institution_name": "我是团长2",
          "settle_colonel_commission": "1000",
          "settle_colonel_tech_service_fee": "100",
          "settle_second_colonel_commission": "50",
          "settle_time": "2006-01-02 15:04:05",
          "shop_id": "12230",
          "short_id": "1231233",
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
