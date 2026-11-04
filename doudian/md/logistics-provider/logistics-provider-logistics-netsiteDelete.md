# 网点信息停用

> logistics.netsiteDelete — 网点信息停用

| 元信息 | 值 |
| --- | --- |
| 中文名 | 网点信息停用 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-netsiteDelete` |
| 接口 ID | `doudian.logistics-provider.logistics.netsiteDelete` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/netsiteDelete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6938 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `net_codes` | body | array | 是 | 网点编码列表 | `["123456"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/netsiteDelete?app_key=your_appkey_here&method=logistics.netsiteDelete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 要删除的网点太多，每次最多允许100个（sub_code: isv.business-failed:4006） | 修改参数网点大小，再调用 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "要删除的网点太多，每次最多允许100个"
}
```

## 备注
