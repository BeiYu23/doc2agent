# ToC出库回告预校验

> yunc.preCheckOutboundFeedback — ToC出库回告预校验接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | ToC出库回告预校验 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-preCheckOutboundFeedback` |
| 接口 ID | `doudian.warehouse.yunc.preCheckOutboundFeedback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/preCheckOutboundFeedback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/7387 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outbound_order_no` | body | string | 是 | 出库单号 | `OB763843789875838983` |
| `sn_order_check_info` | body | object | 否 | 国补订单待校验信息(非国补SN订单，可以为空) | `` |
| `  └ sn_code` | body | string | 是 | SN码 | `S9457489789789` |
| `  └ imei_list` | body | array | 否 | Imei信息（非必填，应传尽传） | `["22439089088","45989u8934"]` |
| `  └ additional_sn_infos` | body | array | 否 | 附加SN信息，主要针对空调品类场景需要区分内机和外机的SN，空调品类国补场景内机和外机SN都必传。 | `` |
| `    └ sn_type` | body | mixed | 是 | 1-内机SN  2-外机SN | `1` |
| `    └ sn_code` | body | string | 是 | SN码 | `S9457489789789` |
| `  └ bar_code` | body | string | 是 | 货品69码 | `69837378979283` |
| `warehouse_code` | body | string | 是 | 仓Code | `V1068` |
| `express_check_info` | body | array | 否 | 快递商待校验信息（如单据下发时货品明细商未指定快递商，可以为空，否则必传） | `` |
| `  └ express_code` | body | string | 否 | 使用的快递商Code | `shunfeng` |
| `  └ cargo_code` | body | string | 否 | 货品Code | `7898793749878945423` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/preCheckOutboundFeedback?app_key=your_appkey_here&method=yunc.preCheckOutboundFeedback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 校验结果 | `` |
| `code` | mixed | 0：正常 | `错误码` |
| `msg` | string | 错误信息 | `系统错误` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1004） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 内部错误（sub_code: isv.business-failed:1001） | 请重试 |
| `20001` | 内部服务超时 / 内部错误（sub_code: isp.service-timeout-error:1204） | 请重试 |
| `50002` | 业务处理失败 / 单据不存在（sub_code: isv.business-failed:1012） | 检查仓Code和出库单号是否正确后重试 |
| `50002` | 业务处理失败 / SN码校验失败（sub_code: isv.business-failed:4021） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "错误码",
    "data": {
      "failed_reason": "未使用指定的快递商",
      "result": "1",
      "sn_order_check_result": {
        "imei_list": "[38907948987,87979790083]",
        "occupy_available": "true/false",
        "platform_order_no": "688368268496537867",
        "sn_code": "S9457489789789"
      }
    },
    "msg": "系统错误"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1004",
  "sub_msg": "参数错误"
}
```

## 备注
