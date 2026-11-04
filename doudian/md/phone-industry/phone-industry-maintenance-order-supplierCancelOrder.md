# maintenance.order.supplierCancelOrder

> 服务商主动取消订单事件

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.phone-industry.maintenance.order.supplierCancelOrder` |
| 中文名 | 服务商主动取消订单事件 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/6642 |
| 更新日期 | `2024-06-20` |

## 接口说明

- 文档书: 手机行业管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `express_code` | body | string | 否 | 寄回物流公司code，寄修收货后取消必传 | `"SF"` |
| `operation_no` | body | string | 是 | 实操单号 | `"BSO35476576"` |
| `operate_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `2024-02-12 12:12:56` |
| `cancel_code` | body | mixed | 是 | 取消原因枚举：1-超出服务保障范围，2-超出权益服务次数 | `1` |
| `track_no` | body | string | 否 | 寄回物流运单号，寄修收货后取消必传 | `"SF32543654"` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `"test"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.order.supplierCancelOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
