# crossBorder.DeleteProductRecord

> 删除备案

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossBorder.DeleteProductRecord` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/DeleteProductRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6182 |
| 更新日期 | `2024-02-23` |

## 接口说明

- 文档书: 跨境API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `record_id_list` | body | array | 是 | 备案ID列表，最多20个 | `["7328268896950550828","7328268896950550829"]` |
| `extra` | body | string | 是 | 额外信息 | `{"示例":""}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/DeleteProductRecord?app_key=your_appkey_here&method=crossBorder.DeleteProductRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 返回码 | `0` |
| `msg` | string | 返回结果描述 | `-` |
| `success_list` | array | 删除成功的备案ID列表 | `["7328268896950550828","7328268896950550829"]` |
| `fail_list` | array | 删除失败的备案ID列表与对应失败原因 | `` |
| `extra` | string | 额外信息 | `{"示例":""}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 内部系统异常（sub_code: isp.service-error:10000） | 重试，多次失败联系平台处理 |
| `60000` | 触发限流，请稍后重试 / 达到qps上限，触发限流（sub_code: isp.traffic-limited:10002） | 重试，并调整流量，控制QPS符合平台要求 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:20000） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 业务处理异常，如备案审核状态不正确、备案不存在、仓所属口岸与传入口岸不一致等（sub_code: isv.business-failed:30000） | 结合返回信息处理，有疑问联系平台处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "extra": {},
    "fail_list": [
      {
        "fail_reason": "1.FailReason字符串最大长度1000 2.失败原因: - 备案不存在 - 备案审核状态不合法 - 备案关联了在途履约单(预约到货单、提货单) - 系统繁忙(DB访问异常/RPC调用异常)",
        "record_id": "7328268896950550830"
      }
    ],
    "msg": "-",
    "success_list": "[\"7328268896950550828\",\"7328268896950550829\"]"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10000",
  "sub_msg": "内部系统异常"
}
```

## 备注
