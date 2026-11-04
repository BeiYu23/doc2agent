# power.notifyRelationTicket

> 物流商关联工单推送（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.notifyRelationTicket` |
| 中文名 | 物流商关联工单推送（仅用于兼容老物流网关 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/notifyRelationTicket` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1560 |
| 更新日期 | `2021-12-27` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bp_ticket_id` | body | string | 是 | - | `0` |
| `track_no` | body | string | 是 | - | `0` |
| `ticket_create_first_type` | body | string | 否 | - | `0` |
| `ticket_create_second_type` | body | string | 否 | - | `0` |
| `ticket_create_third_type` | body | string | 否 | - | `0` |
| `ticket_create_description` | body | string | 是 | - | `0` |
| `ticket_status` | body | string | 是 | - | `0` |
| `ticket_close_first_type` | body | string | 否 | - | `0` |
| `ticket_close_second_type` | body | string | 否 | - | `0` |
| `ticket_close_third_type` | body | string | 否 | - | `0` |
| `ticket_close_description` | body | string | 否 | - | `0` |
| `compensate_state` | body | string | 否 | - | `0` |
| `compensate_amount` | body | number | 否 | - | `0` |
| `product_volume` | body | number | 否 | - | `0` |
| `attachment` | body | array | 否 | - | `0` |
| `extension` | body | string | 否 | - | `0` |
| `request_time` | body | number | 是 | - | `0` |
| `ticket_create_time` | body | number | 是 | - | `0` |
| `ticket_close_time` | body | number | 否 | - | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/notifyRelationTicket?app_key=your_appkey_here&method=power.notifyRelationTicket&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000:工单已完结（sub_code: isv.business-failed:10000） | 10000:工单已完结 |

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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "10000:工单已完结"
}
```

## 备注
