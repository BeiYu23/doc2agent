# 查询服务市场订单

> fuwu.order.list — 查询服务市场订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询服务市场订单 |
| 文档地址 | `/docs/doudian/tool/tool-fuwu-order-list` |
| 接口 ID | `doudian.tool.fuwu.order.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/order/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/4524 |
| 更新日期 | `2023-09-05` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_create_time_start` | body | number | 是 | 要搜索的订单创建时间起，unix秒级时间戳，必须大于2019年1月1日 | `1690819200` |
| `order_create_time_end` | body | number | 是 | 要搜索的订单创建时间止，unix秒级时间戳，需小于次月1日 | `1693497600` |
| `page_index` | body | number | 是 | 页码，从1起 | `1` |
| `page_size` | body | number | 是 | 每页大小，最小1，最大100。 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/order/list?app_key=your_appkey_here&method=fuwu.order.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `orders` | array | 订单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统负载高或查询报错（sub_code: isp.service-error:200） | 稍后重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:100001） | 按照返回描述修改入参 |
| `20001` | 内部服务超时 / 查询报错（sub_code: isp.service-timeout-error:300000） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "orders": [
      {
        "app_id": "7255935913727911234",
        "order_id": "692125073230001234",
        "pay_amount": "0",
        "pay_type": "7",
        "refund_status": "0",
        "service_end_time": "1693727023",
        "service_start_time": "1693122223",
        "shop_id": "77977",
        "sku_duration": "7",
        "sku_duration_unit": "0",
        "sku_price": "0",
        "sku_spec_type": "0",
        "sku_spec_value": "试用版",
        "sku_title": "试用版 7天"
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
  "sub_code": "isp.service-error:200",
  "sub_msg": "系统负载高或查询报错"
}
```

## 备注
