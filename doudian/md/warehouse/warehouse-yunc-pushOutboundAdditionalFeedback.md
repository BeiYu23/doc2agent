# 云仓出库单附属信息回传

> yunc.pushOutboundAdditionalFeedback — 云仓出库单附属信息回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 云仓出库单附属信息回传 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-pushOutboundAdditionalFeedback` |
| 接口 ID | `doudian.warehouse.yunc.pushOutboundAdditionalFeedback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/pushOutboundAdditionalFeedback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/7432 |
| 更新日期 | `2025-12-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `slip_no` | body | string | 是 | 幂等号 需要保证唯一 | `"V0002_OB398798798543343_98798758493"` |
| `option_sn_info` | body | object | 否 | 延迟占用的SN信息 | `` |
| `  └ cargo_code` | body | string | 是 | 货品信息 | `"76823878979875844"` |
| `  └ line_no` | body | string | 是 | 出库单行号 | `"1"` |
| `  └ sn_infos` | body | array | 否 | SN码列表，如有多个SN，需要每次回传全量的SN信息，平台会做覆盖更新 | `` |
| `    └ sn_code` | body | string | 是 | SN码 | `"890788798797898"` |
| `    └ bar_code` | body | string | 否 | 货品条码 | `"89778534353235"` |
| `    └ imei_list` | body | array | 否 | imei信息（应传尽传，实物有多少个就传多少个，如果没有的话可以不传） | `["4532464654","463465464"]` |
| `warehouse_code` | body | string | 是 | 仓Code | `"V0003"` |
| `outbound_order_no` | body | string | 是 | 出库单号 | `"OB898479854934464334"` |
| `occurrence_time` | body | mixed | 是 | 请求的毫秒级时间戳，多次更新场景下用于做版本控制使用。 | `1745828286000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/pushOutboundAdditionalFeedback?app_key=your_appkey_here&method=yunc.pushOutboundAdditionalFeedback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
