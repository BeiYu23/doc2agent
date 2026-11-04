# 物流商推送改约时间

> power.updateCollectTime — 物流商推送改约时间

| 元信息 | 值 |
| --- | --- |
| 中文名 | 物流商推送改约时间 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-updateCollectTime` |
| 接口 ID | `doudian.logistics.power.updateCollectTime` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/updateCollectTime` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1627 |
| 更新日期 | `2026-01-06` |

## 接口说明

- 文档书: 物流发货API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_no` | body | string | 否 | 1 | `1` |
| `start_collect_time` | body | string | 否 | 1 | `1` |
| `end_collect_time` | body | string | 否 | 1 | `1` |
| `operation_time` | body | string | 否 | 1 | `1` |
| `logistics_fulfill_order_no` | body | string | 否 | 1 | `1` |
| `call` | body | boolean | 否 | 1 | `1` |
| `call_nums` | body | string | 否 | 1 | `1` |
| `is_connected` | body | boolean | 否 | 1 | `1` |
| `call_info` | body | array | 否 | 1 | `` |
| `  └ call_number` | body | string | 否 | 1 | `1` |
| `  └ call_duration` | body | string | 否 | 1 | `1` |
| `  └ receive_number` | body | string | 否 | 1 | `1` |
| `  └ caller_name` | body | string | 否 | 1 | `1` |
| `  └ is_connected` | body | boolean | 否 | 1 | `1` |
| `  └ call_time` | body | string | 否 | 1 | `1` |
| `reason` | body | string | 否 | 改约原因 | `UNABLE_TO_CONTACT_CONSUMER` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/updateCollectTime?app_key=your_appkey_here&method=power.updateCollectTime&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -10007:未知错误（sub_code: isv.business-failed:-10007） | 人工定位 |
| `50002` | 业务处理失败 / 10902:该运单号已超过修改次数阈值（sub_code: isv.business-failed:10902） | 修改失败 |
| `50002` | 业务处理失败 / 10905:修改时间不在3天内（sub_code: isv.business-failed:10905） | 修改失败 |
| `50002` | 业务处理失败 / 6405:系统异常（sub_code: isv.business-failed:6405） | 修改失败 |
| `50002` | 业务处理失败 / 10904:修改时间格式不允许（sub_code: isv.business-failed:10904） | 修改失败 |
| `50002` | 业务处理失败 / 10901:当前状态不允许修改（sub_code: isv.business-failed:10901） | 修改失败 |
| `50002` | 业务处理失败 / 10002:系统异常（sub_code: isv.business-failed:10002） | 人工定位 |
| `50002` | 业务处理失败 / 10906:不满足电联要求（sub_code: isv.business-failed:10906） | 传入合法电联记录 |
| `50002` | 业务处理失败 / 10000:参数错误（sub_code: isv.business-failed:10000） | 检查参数 |
| `50002` | 业务处理失败 / 滞留包裹不支持改约（sub_code: isv.business-failed:10907） | 检查参数 |
| `50002` | 业务处理失败 / 1h不支持改为2h预约时间（sub_code: isv.business-failed:10014） | 检查参数 |
| `50002` | 业务处理失败 / 当前状态不支持上报“无法联系上消费者”（sub_code: isv.business-failed:10921） | 修改失败 |
| `50002` | 业务处理失败 / 当前状态不支持上报“消费者想换寄件时间”（sub_code: isv.business-failed:10922） | 修改失败 |
| `50002` | 业务处理失败 / 当前状态不支持上报“来不及按预约时间上门”（sub_code: isv.business-failed:10923） | 修改失败 |
| `50002` | 业务处理失败 / 提报时间必须晚于用户预约的最晚上门时间（sub_code: isv.business-failed:10924） | 修改失败 |

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
  "sub_code": "isv.business-failed:-10007",
  "sub_msg": "-10007:未知错误"
}
```

## 备注
