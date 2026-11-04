# <接口名称>

> 一句话说明这个接口做什么。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `<platform>.<resource>.<action>` |
| 平台 | `<platform>` |
| 请求方法 | `GET` / `POST` |
| 接口路径 | `/v1/example/path` |
| Base URL | `https://example.com` |
| 鉴权方式 | `cookie` / `token` / `sign` / `none` |
| 文档来源 | <来源链接或「自测整理」> |
| 更新日期 | `YYYY-MM-DD` |

## 接口说明

补充说明：适用场景、调用前置条件、频率限制、注意事项。

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `param_a` | query | string | 是 | 参数 A 的含义 | `abc123` |
| `param_b` | body | number | 否 | 参数 B 的含义 | `20` |

参数说明：

- 位置取值：`query` / `body` / `header` / `path`。
- 无参数的接口写「无参数」，保留表头。

## 请求示例

```bash
curl -X GET 'https://example.com/v1/example/path?param_a=abc123' \
  -H 'Authorization: Bearer <TOKEN>'
```

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `0` | 成功 | 正常读取 data |
| `1001` | 参数缺失 | 核对必填参数 |
| `401` | 未登录 / 凭证失效 | 刷新凭证后重试 |
| `429` | 请求过于频繁 | 退避重试，降低频率 |
| `500` | 服务端错误 | 记录日志，稍后重试 |

## 响应示例

成功：

```json
{
  "code": 0,
  "message": "success",
  "data": {
    "id": "abc123",
    "name": "示例数据"
  }
}
```

失败：

```json
{
  "code": 1001,
  "message": "missing required param: param_a",
  "data": null
}
```

## 备注

- 字段语义、坑、版本差异等零散信息写在这里；没有可写「无」。
