# logistics.pushLogisticsData

> 推送数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.pushLogisticsData` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushLogisticsData` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6035 |
| 更新日期 | `2024-01-15` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 单号 | `xxx` |
| `biz_type` | body | string | 是 | 业务类型 1. 1-收货偏好 | `1` |
| `sub_biz_type` | body | string | 是 | 1 - 推送收货偏好下发的履约结果 2 - 小程序偏好下发推送接口 | `1` |
| `express` | body | string | 是 | 快递公司名称 | `xxx` |
| `track_no` | body | string | 是 | 运单号 | `xxx` |
| `operation_time` | body | string | 是 | 操作时间。格式：YYYY-MM-DD HH24:MM:SS | `2020-11-11 22:00:00` |
| `param` | body | string | 是 | 不同业务传不同结构体的Json String biz_type + sub_biz_type 拿具体的结构体去反序列化 | `详细参数` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/pushLogisticsData?app_key=your_appkey_here&method=logistics.pushLogisticsData&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 状态码 | `0` |
| `message` | string | 状态码描述 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "成功"
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
