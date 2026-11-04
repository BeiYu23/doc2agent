# 商家分次结算订单

> buyin.shopMultiSettlementOrders — 商家分次结算订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家分次结算订单 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-shopMultiSettlementOrders` |
| 接口 ID | `doudian.alliance.buyin.shopMultiSettlementOrders` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/shopMultiSettlementOrders` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2703 |
| 更新日期 | `2023-04-18` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | number | 否 | 查询数目，最大100 | `50` |
| `cursor` | body | string | 否 | 下一页索引，第一页传‘0’ | `0` |
| `time_type` | body | string | 否 | 查询时间类型：settle（结算时间），update（更新时间，默认值） | `settle` |
| `start_time` | body | string | 否 | 开始时间 | `2022-10-01 00:00:00` |
| `end_time` | body | string | 否 | 结束时间，与开始时间相差不能超过90天 | `2022-10-31 00:00:00` |
| `order_ids` | body | string | 否 | 订单号列表 | `4994437582409747777,4994437582409747776,4994437582409747775` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/shopMultiSettlementOrders?app_key=your_appkey_here&method=buyin.shopMultiSettlementOrders&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
      "cursor": "4387239",
      "orders": [
        {
          "ads_buyin_id": "7878990233322",
          "author_account": "作者账号",
          "author_buyin_id": "79849389438430",
          "colonel_activity_id": "302931",
          "colonel_buyin_id": "78790909302931",
          "colonel_institution_name": "我是团长",
          "distribution_type": "directIn",
          "is_stepped_plan": "false",
          "order_id": "4994437582409747775",
          "phase_id": "2",
          "pid": "dy_102222_23333",
          "product_id": "3450632721376902816",
          "product_name": "测试商品",
          "real_service_fee": "1000",
          "settle_ads_commission": "0",
          "settle_ads_tech_service_fee": "100",
          "settle_colonel_commission": "200",
          "settle_colonel_tech_service_fee": "3",
          "settle_shop_commission": "1000",
          "settle_time": "2006-01-02 15:04:05",
          "shop_id": "12230",
          "short_id": "2334433",
          "site_name": "微信",
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
