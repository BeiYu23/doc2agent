# logistics.updateCollectTime

> 物流商推送改约时间

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.updateCollectTime` |
| 中文名 | 物流商推送改约时间 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/updateCollectTime` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7187 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_no` | body | string | 否 | 运单号 | `JT0101001010` |
| `start_collect_time` | body | string | 否 | 开始揽收时间 | `2021-01-19 09:00:00` |
| `end_collect_time` | body | string | 否 | 结束揽收时间 | `2021-01-19 10:00:00` |
| `operation_time` | body | string | 否 | 操作时间 | `2021-01-19 15:12:23` |
| `logistics_fulfill_order_no` | body | string | 否 | 物流领域订单id | `LFO000000000001` |
| `is_connected` | body | boolean | 否 | 是否接通 | `true` |
| `express` | body | string | 否 | 物流商 | `shunfeng` |
| `call` | body | boolean | 否 | 是否电联 | `true` |
| `call_nums` | body | string | 否 | 电联次数 | `1` |
| `call_info` | body | array | 否 | 电联信息 | `` |
| `  └ caller_name` | body | string | 否 | 电联人姓名（快递员） | `张三` |
| `  └ receive_number` | body | string | 否 | 用户号码 | `15161052777` |
| `  └ is_connected` | body | boolean | 否 | 是否接通 | `true` |
| `  └ call_time` | body | string | 否 | 电联时间 | `2021-01-19 10:00:00` |
| `  └ call_duration` | body | string | 否 | 通话时长 | `10（秒）` |
| `  └ call_number` | body | string | 否 | 电联号码（快递员） | `15161052777` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/updateCollectTime?app_key=your_appkey_here&method=logistics.updateCollectTime&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
