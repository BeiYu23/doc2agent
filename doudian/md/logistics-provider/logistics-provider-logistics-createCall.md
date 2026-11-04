# 派前电联创建呼叫

> logistics.createCall — 派前电联创建呼叫接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 派前电联创建呼叫 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-createCall` |
| 接口 ID | `doudian.logistics-provider.logistics.createCall` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/createCall` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2876 |
| 更新日期 | `2023-01-09` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `call_list` | body | array | 是 | 呼叫列表 | `` |
| `  └ waybill_no` | body | string | 是 | 运单号 | `75510000017219` |
| `  └ biz_type` | body | string | 是 | "callBeforeDelivery"-派前电联 | `callBeforeDelivery` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/createCall?app_key=your_appkey_here&method=logistics.createCall&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "msg": "参数错误",
        "status": "0",
        "waybill_no": "75510000019316"
      }
    ]
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
