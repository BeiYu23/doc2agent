# logistics.majorAppliances.ReGenerateVirtualPhone

> 重新生成虚拟号

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.logistics.majorAppliances.ReGenerateVirtualPhone` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8309 |
| 更新日期 | `2026-05-18` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pickup_order_id` | body | string | 否 | 取件单号 | `LBFxxxxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.majorAppliances.ReGenerateVirtualPhone&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result_type` | mixed | 获取结果类型：1-原虚拟号(未过期情况);2-新虚拟号(过期情况)；3-生成虚拟号失败(过期情况) | `2` |
| `virtual_phone` | string | 用户手机虚拟号 | `700xxxxxxx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "result_type": "2",
    "virtual_phone": "700xxxxxxx"
  },
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
