# buyin.commonShareCommandParse

> 该接口用于解析抖口令和短链获取口令类型及对应口令信息，可用于解析已经转链过的抖口令和抖音分享的短链。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.commonShareCommandParse` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/commonShareCommandParse` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2627 |
| 更新日期 | `2023-04-25` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=buyin.commonShareCommandParse&param_json={}'
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
