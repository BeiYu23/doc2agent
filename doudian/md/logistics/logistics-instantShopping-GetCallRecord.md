# instantShopping.GetCallRecord

> 查询骑手-用户通话记录

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.instantShopping.GetCallRecord` |
| 中文名 | 查询骑手-用户通话记录 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/7155 |
| 更新日期 | `2024-12-17` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `delivery_id` | body | string | 否 | 运单id | `a_1234` |
| `distributor_code` | body | string | 否 | 配送商code | `AAA` |
| `distributor_rider_id` | body | mixed | 否 | 骑手id | `123` |
| `exception_code` | body | mixed | 否 | 异常报备code | `1001` |
| `exception_descr` | body | string | 否 | 异常报备描述 | `异常情况1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.GetCallRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `record_list` | array | 通话记录集合 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "record_list": [
      {
        "call_result": "0",
        "call_start_time": "1732000000",
        "is_call_receipt": "false",
        "rider_name": "张三",
        "rider_phone": "13911112222",
        "ring_time": "1732000000",
        "ring_time_duration": "10"
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
