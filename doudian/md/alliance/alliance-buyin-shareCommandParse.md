# 商品口令转商品解析

> buyin.shareCommandParse — 商品口令转商品解析

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品口令转商品解析 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-shareCommandParse` |
| 接口 ID | `doudian.alliance.buyin.shareCommandParse` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/shareCommandParse` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1726 |
| 更新日期 | `2024-04-11` |

## 接口说明

- 文档书: 精选联盟API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?method=buyin.shareCommandParse&param_json={}'
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
