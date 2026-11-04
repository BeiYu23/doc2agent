# 质检机构_实物质检订单发货

> btas.sc.shippingOrQueryOrderERP — 质检机构_实物质检订单发货（废弃）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 质检机构_实物质检订单发货 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-sc-shippingOrQueryOrderERP` |
| 接口 ID | `doudian.btas-inspect.btas.sc.shippingOrQueryOrderERP` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/shippingOrQueryOrderERP` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2945 |
| 更新日期 | `2023-02-09` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=btas.sc.shippingOrQueryOrderERP&param_json={}'
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
