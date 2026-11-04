# 查询卡券（无需授权

> coupons.query — 查询卡券（无需授权）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询卡券（无需授权 |
| 文档地址 | `/docs/doudian/coupon/coupon-coupons-query` |
| 接口 ID | `doudian.coupon.coupons.query` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/query` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/7584 |
| 更新日期 | `2025-07-10` |

## 接口说明

- 文档书: 卡券API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `supplier_code` | body | string | 否 | 服务商Code | `112233` |
| `virtual_no_list` | body | array | 是 | 卡券号 | `["112233"]` |
| `query_type` | body | mixed | 是 | 查询方式(仅支持卡券号查询，参数赋值为2) | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/query?app_key=your_appkey_here&method=coupons.query&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `virtual_order_info_list` | array | 卡券列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:000002） | 传正确参数 |

## 响应示例

成功：

```json
{
  "data": {
    "virtual_order_info_list": [
      {
        "cert_no": "112233",
        "order_id": "6900002012222",
        "shop_id": "1234435"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:000002",
  "sub_msg": "参数错误"
}
```

## 备注
