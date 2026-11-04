# batchCallback接口（仅用于兼容老物…

> power.batchCallback — batchCallback接口（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | batchCallback接口（仅用于兼容老物… |
| 文档地址 | `/docs/doudian/logistics/logistics-power-batchCallback` |
| 接口 ID | `doudian.logistics.power.batchCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/batchCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1548 |
| 更新日期 | `2021-12-17` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `param` | body | string | 是 | xxx | `xxx` |
| `sign` | body | string | 是 | xxx | `xxx` |
| `company` | body | string | 是 | xxx | `xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/batchCallback?app_key=your_appkey_here&method=power.batchCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10001:请求基础参数错误（sub_code: isv.business-failed:10001） | 10001:请求基础参数错误 |

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
  "sub_code": "isv.business-failed:10001",
  "sub_msg": "10001:请求基础参数错误"
}
```

## 备注
