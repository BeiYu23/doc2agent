# btas.sc.confirmReceiveOfflineOrders

> 质检机构_确认收货(实物质检订单）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.sc.confirmReceiveOfflineOrders` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/confirmReceiveOfflineOrders` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2922 |
| 更新日期 | `2023-02-09` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orders` | body | array | 是 | 订单列表 | `` |
| `  └ order_code` | body | string | 是 | 订单码 | `"12313111"` |
| `  └ product_quantity` | body | string | 是 | 商品数量 | `1` |
| `sc_id` | body | number | 是 | 质检机构ID。请填入当前订单对应的 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/activitySearch?app_key=your_appkey_here&method=buyin.activitySearch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `orders` | array | 订单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 3006:全部收货失败（sub_code: isv.business-failed:3006） | 3006:全部收货失败 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_list": [
      {
        "activity_desc": "无要求",
        "activity_id": "23123123123",
        "activity_name": "测试活动",
        "activity_status": "0",
        "activity_status_desc": "任意状态",
        "apply_end_time": "2021/1/16",
        "apply_start_time": "2021/1/16",
        "categories_limit": "\"\"",
        "commission_rate": "10",
        "estimated_single_sale": "500",
        "institution_name": "测试机构1",
        "new_shop_limit": "可报名",
        "product_activity_ratio": "10.11",
        "promote_end_time": "2021/1/16",
        "promote_start_time": "2021/1/16",
        "service_rate": "10",
        "service_ratio": "10.11",
        "shop_score_limit": "\"0\"",
        "shop_type_limit": "\"\""
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:3006",
  "sub_msg": "3006:全部收货失败"
}
```

## 备注
