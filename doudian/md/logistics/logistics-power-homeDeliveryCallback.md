# power.homeDeliveryCallback

> 送货上门履约结果推送（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.homeDeliveryCallback` |
| 中文名 | 送货上门履约结果推送（仅用于兼容老物流网关 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/homeDeliveryCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1573 |
| 更新日期 | `2022-11-08` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `resource_code` | body | string | 否 | - | `0` |
| `waybill_no` | body | string | 否 | - | `0` |
| `number_calls` | body | string | 否 | - | `0` |
| `is_connected` | body | string | 否 | - | `0` |
| `connect_result` | body | string | 否 | - | `0` |
| `time_ring_list` | body | array | 否 | - | `` |
| `  └ is_connected` | body | string | 否 | - | `0` |
| `  └ time_ring` | body | string | 否 | - | `0` |
| `is_home_delivery` | body | string | 否 | - | `0` |
| `home_delivery_remark` | body | string | 否 | - | `0` |
| `photograph` | body | string | 否 | 签收图片 | `1` |
| `biz_type` | body | string | 否 | 业务类型 | `SignAndReturn` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10003:系统异常（sub_code: isv.business-failed:10003） | 10003:系统异常 |

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
  "sub_code": "isv.business-failed:10003",
  "sub_msg": "10003:系统异常"
}
```

## 备注
