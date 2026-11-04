# 物流商推送改约时间

> logistics.overSize.updateCollectTime — 物流商推送改约时间

| 元信息 | 值 |
| --- | --- |
| 中文名 | 物流商推送改约时间 |
| 文档地址 | `/docs/doudian/pickup/pickup-logistics-overSize-updateCollectTime` |
| 接口 ID | `doudian.pickup.logistics.overSize.updateCollectTime` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1526/6708 |
| 更新日期 | `2024-07-29` |

## 接口说明

- 文档书: 上门取件API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `is_connected` | body | boolean | 否 | 是否接通 | `true` |
| `call_info` | body | array | 否 | 每次电联的明细 | `` |
| `  └ call_duration` | body | string | 否 | 通话时长 | `10` |
| `  └ call_number` | body | string | 否 | 电联号码（快递员） | `15161052777` |
| `  └ caller_name` | body | string | 否 | 电联人姓名（快递员） | `张三` |
| `  └ receive_number` | body | string | 否 | 15161052777 | `电联人姓名（快递员）` |
| `  └ is_connected` | body | boolean | 否 | 是否接通 | `true` |
| `  └ call_time` | body | string | 否 | 电联时间 | `2021-01-19 10:00:00` |
| `logistics_fulfill_order_no` | body | string | 否 | 物流领域订单id | `LFO000000000001` |
| `call` | body | boolean | 否 | 是否电联 | `true` |
| `call_nums` | body | string | 否 | 电联次数 | `1` |
| `waybill_no` | body | string | 否 | 运单号 | `JT0101001010` |
| `start_collect_time` | body | string | 否 | 开始揽收时间 | `2021-01-19 09:00:00` |
| `end_collect_time` | body | string | 否 | 结束揽收时间 | `2021-01-19 09:00:00` |
| `operation_time` | body | string | 否 | 修改操作时间 | `2021-01-19 15:12:23` |
| `express` | body | string | 否 | 物流商 | `debangkuaiyun` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.overSize.updateCollectTime&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 11710:当前状态不允许变更（sub_code: isv.business-failed:11710） | 推送正确状态 |
| `50002` | 业务处理失败 / 10000:参数错误（sub_code: isv.business-failed:10000） | 推送正确状态 |
| `50002` | 业务处理失败 / 11714:当前状态已取消不允许更新（sub_code: isv.business-failed:11714） | 推送正确状态 |
| `50002` | 业务处理失败 / 11715:当前状态已取消不允许更新（sub_code: isv.business-failed:11715） | 推送正确状态 |
| `50002` | 业务处理失败 / 11713:重复拦截（sub_code: isv.business-failed:11713） | 推送正确状态 |
| `50002` | 业务处理失败 / 6405:系统错误（sub_code: isv.business-failed:6405） | 重试 |
| `50002` | 业务处理失败 / -10007:未知错误（sub_code: isv.business-failed:-10007） | 重试 |
| `50002` | 业务处理失败 / 重量异常，重新输入重量信息（sub_code: isv.business-failed:11719） | 重新推送核价 |
| `50002` | 业务处理失败 / 重复核重核价（sub_code: isv.business-failed:11718） | 不需要推送核价 |
| `50002` | 业务处理失败 / 重复揽收（sub_code: isv.business-failed:11712） | 不允许推送揽收 |
| `50002` | 业务处理失败 / 当前状态不允许修改（sub_code: isv.business-failed:10901） | 推送正确状态 |
| `50002` | 业务处理失败 / 该运单号已超过修改次数阈值（sub_code: isv.business-failed:10902） | 推送正确状态 |
| `50002` | 业务处理失败 / 当天修改次数已达阈值（sub_code: isv.business-failed:10903） | 推送正确状态 |
| `50002` | 业务处理失败 / 修改时间格式不允许（sub_code: isv.business-failed:10904） | 推送正确状态 |
| `50002` | 业务处理失败 / 修改时间不在3天内（sub_code: isv.business-failed:10905） | 推送正确状态 |
| `50002` | 业务处理失败 / 不满足改约电联要求（sub_code: isv.business-failed:10906） | 推送正确状态 |
| `50002` | 业务处理失败 / 滞留包裹不支持改约（sub_code: isv.business-failed:10907） | 推送正确状态 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:10002） | 重试 |
| `50002` | 业务处理失败 / 1h改约单仅支持1h改约（sub_code: isv.business-failed:10014） | 推送正确状态 |

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
  "sub_code": "isv.business-failed:11710",
  "sub_msg": "11710:当前状态不允许变更"
}
```

## 备注
