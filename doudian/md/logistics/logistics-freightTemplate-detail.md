# freightTemplate.detail

> 获取运费模板详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.freightTemplate.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/freightTemplate/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2157 |
| 更新日期 | `2025-03-11` |

## 接口说明

- 文档书: 物流发货API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `freight_id` | body | mixed | 是 | 模板id | `3748974` |
| `query_option` | body | object | 否 | 查询请求 | `` |
| `  └ query_transfer_rule` | body | boolean | 是 | 是否查询中转规则，默认false | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/freightTemplate/detail?app_key=your_appkey_here&method=freightTemplate.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 模板详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 模板丢失（sub_code: isp.service-error:3） | 模板丢失 |
| `20000` | 系统错误 / 模板未找到（sub_code: isp.service-error:2） | 模板未找到 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:3",
  "sub_msg": "模板丢失"
}
```

## 备注
