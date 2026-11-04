# ddp_open.ai.reportUsage

> 上报商家用量

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.ddp_open.ai.reportUsage` |
| 中文名 | 上报商家用量 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/ddp_open/ai/reportUsage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8357 |
| 更新日期 | `2026-06-04` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `total_cnt` | body | string | 否 | 总可用 = used_cnt+remain_cnt+freezing_cnt | `10.05` |
| `used_cnt` | body | string | 否 | 已使用 | `0.05` |
| `remain_cnt` | body | string | 否 | 剩余可用 | `9` |
| `freezing_cnt` | body | string | 否 | 不可用（冻结） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/ddp_open/ai/reportUsage?app_key=your_appkey_here&method=ddp_open.ai.reportUsage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
