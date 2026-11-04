# power.register

> 订阅物流（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.register` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/register` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1475 |
| 更新日期 | `2021-11-24` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `param_json` | body | string | 是 | - | `-` |
| `app_id` | body | number | 是 | - | `1` |
| `sign` | body | string | 是 | - | `-` |
| `v` | body | string | 是 | - | `1` |
| `timestamp_compatible` | body | number | 是 | - | `1111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/register?app_key=your_appkey_here&method=power.register&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 400:数据错误（sub_code: isv.business-failed:400） | 400:数据错误 |
| `50002` | 业务处理失败 / 501:重复订阅（sub_code: isv.business-failed:501） | 501:重复订阅 |

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
  "sub_code": "isv.business-failed:400",
  "sub_msg": "400:数据错误"
}
```

## 备注
