# 查询订单账单明细11.31下线

> order.settle — 查询订单账单明细11.31下线

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询订单账单明细11.31下线 |
| 文档地址 | `/docs/doudian/bill/bill-order-settle` |
| 接口 ID | `doudian.bill.order.settle` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/settle` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/204 |
| 更新日期 | `2021-08-03` |

## 接口说明

- 文档书: 账单API（版本 ）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=order.settle&param_json={}'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "code": 10000,
  "msg": "success"
}
```

失败：

```json
{
  "code": 40004,
  "msg": "非法的参数"
}
```

## 备注
