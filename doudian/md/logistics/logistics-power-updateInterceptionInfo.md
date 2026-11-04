# 拦截成功退回结果回传接口（仅用于兼容老物流网关

> power.updateInterceptionInfo — 拦截成功退回结果回传接口（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 拦截成功退回结果回传接口（仅用于兼容老物流网关 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-updateInterceptionInfo` |
| 接口 ID | `doudian.logistics.power.updateInterceptionInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/updateInterceptionInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1480 |
| 更新日期 | `2021-11-24` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id_compatible` | body | number | 否 | 店铺Id | `1234` |
| `resource_code` | body | string | 否 | 运单号 | `1234567890000` |
| `waybill_no` | body | string | 否 | 物流服务商资源编码 | `11111` |
| `return_result` | body | string | 否 | 退回结果 | `1` |
| `result_code` | body | string | 否 | 退回失败原因编码 | `10001` |
| `result_message` | body | string | 否 | 退回失败原因信息 | `用户签收` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/updateInterceptionInfo?app_key=your_appkey_here&method=power.updateInterceptionInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10006:当前状态不允许变更（sub_code: isv.business-failed:10006） | 10006:当前状态不允许变更 |
| `50002` | 业务处理失败 / 10000:参数错误（sub_code: isv.business-failed:10000） | 10000:参数错误 |
| `50002` | 业务处理失败 / 10002:系统异常（sub_code: isv.business-failed:10002） | 10002:系统异常 |

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
  "sub_code": "isv.business-failed:10006",
  "sub_msg": "10006:当前状态不允许变更"
}
```

## 备注
