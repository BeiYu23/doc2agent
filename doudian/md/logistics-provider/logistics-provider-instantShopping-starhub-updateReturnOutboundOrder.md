# instantShopping.starhub.updateReturnOutboundOrder

> 退供出库场景，服务商通知抖音退仓出库单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.instantShopping.starhub.updateReturnOutboundOrder` |
| 中文名 | 退供出库场景，服务商通知抖音退仓出库单状态 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7023 |
| 更新日期 | `2024-10-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `return_order_id` | body | string | 是 | 退仓出库主单ID | `12414124124` |
| `return_order_type` | body | mixed | 否 | 单据类型 - 1：退仓出库 | `1` |
| `sub_orders` | body | array | 否 | 出库子单(明细)，当200状态下必传 | `` |
| `  └ return_sub_order_id` | body | string | 否 | 退仓出库子单ID(行号) | `123123123` |
| `  └ production_time` | body | mixed | 否 | 生产日期，秒级时间戳(当200情况下必填) | `1724817747` |
| `  └ expire_day` | body | mixed | 否 | 保质期（天）(当200情况下必填) | `10` |
| `  └ receive_time` | body | mixed | 否 | 入库时间，秒级时间戳(当200情况下必填) | `1724817747` |
| `  └ outbound_count` | body | mixed | 否 | 实际出库数量(当200情况下必填，不允许超发，允许少发可以为0) | `20` |
| `operator_name` | body | string | 否 | 操作人姓名 | `xxx` |
| `status` | body | mixed | 否 | 单据状态，参考状态机 | `200` |
| `update_time` | body | mixed | 否 | 业务时间，秒级时间戳 | `1724817747` |
| `attachments` | body | array | 否 | 附件信息 | `` |
| `  └ attachment_name` | body | string | 否 | 附件名 | `xxx退仓出库说明` |
| `  └ attachment_url` | body | string | 否 | 附件资源下载URL | `https://xxx.docx` |
| `  └ attachment_type` | body | mixed | 否 | 附件类型 1:文件 2:图片 3:视频 | `1` |
| `operator_id` | body | string | 否 | 能定位到服务商操作人的唯一键 | `1232131` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.starhub.updateReturnOutboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40001） | 传入合法入参 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "参数错误"
}
```

## 备注
