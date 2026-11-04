# logistics.createSFOrder

> 顺丰新下单接口，建议顺丰下单都走该接口，功能更齐全

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.createSFOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/createSFOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1847 |
| 更新日期 | `2021-03-15` |

## 接口说明

- 文档书: 电子面单API（版本 V1.08）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=logistics.createSFOrder&param_json={}'
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
