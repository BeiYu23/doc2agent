# alliance.getOrderList

> 查询联盟订单明细

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.getOrderList` |
| 中文名 | 查询联盟订单明细 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/getOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/469 |
| 更新日期 | `2024-06-13` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_ids` | body | array | 是 | 订单id列表 | `[\"id1\",\"id2\",\"id3\"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/getOrderList?app_key=your_appkey_here&method=alliance.getOrderList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回编码 | `100000` |
| `code_msg` | string | 返回信息 | `success` |
| `datas` | array | 订单明细数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "100000",
    "code_msg": "success",
    "datas": [
      {
        "alliance_biz_type": "COMMON",
        "author_account": "北三环小王子",
        "commission_rate": "300",
        "estimated_comission": "810",
        "order_id": "4790957107260097836",
        "order_status": "支付成功",
        "phase_id": "1",
        "product_id": "3475285904548040556",
        "real_comission": "0",
        "shop_id": "1111115516",
        "short_id": "1068048",
        "total_pay_amount": "31000"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
