# CC查身份证

> crossBorder.getIdentification — CC查身份证

| 元信息 | 值 |
| --- | --- |
| 中文名 | CC查身份证 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-crossBorder-getIdentification` |
| 接口 ID | `doudian.cross-border.crossBorder.getIdentification` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/getIdentification` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6648 |
| 更新日期 | `2024-06-28` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=crossBorder.getIdentification&param_json={}'
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
