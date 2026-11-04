# 跨境服务商回传增值服务单数据

> crossBorder.notifyValueAddedOrderOrder — 跨境服务商回传增值服务单数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 跨境服务商回传增值服务单数据 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-crossBorder-notifyValueAddedOrderOrder` |
| 接口 ID | `doudian.cross-border.crossBorder.notifyValueAddedOrderOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/notifyValueAddedOrderOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/5776 |
| 更新日期 | `2023-11-29` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `value_added_order_no` | body | string | 是 | 增值服务单号 | `VA149289045390` |
| `event_type` | body | number | 是 | 事件类型 2-待审核 3-审核不通过 4-审核通过 5-作业中 6-已完成 | `1` |
| `warehouse_code` | body | string | 是 | 仓编号 | `W001` |
| `biz_order_no` | body | string | 是 | 唯一流水号 | `123456` |
| `occur_time` | body | number | 是 | 事件发生时间 秒级时间戳 | `1664193365` |
| `operator` | body | string | 是 | 操作人 | `test` |
| `details` | body | array | 是 | 增值服务详情 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `1` |
| `  └ actual_qty` | body | number | 否 | 实际数量 | `11` |
| `  └ cargo_code` | body | string | 否 | 货品编码 | `711232943959456` |
| `  └ estimated_qty` | body | number | 否 | 预估数量 | `11` |
| `expect_num` | body | number | 否 | 计划份数 | `10` |
| `actual_num` | body | number | 否 | 实际数量 | `10` |
| `reason` | body | string | 否 | 驳回原因 | `审核不通过` |
| `actual_amount` | body | number | 否 | 实际金额 ，单位分 | `111` |
| `attachment_urls` | body | array | 否 | 附件列表 | `` |
| `  └ url` | body | string | 是 | 附件url | `http://sss` |
| `  └ file_name` | body | string | 是 | 附件名称 | `test` |
| `estimated_amount` | body | number | 否 | 预估金额，单位分 | `111` |
| `slip_no` | body | string | 否 | 幂等号 | `1ewdrsdfsd` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/notifyValueAddedOrderOrder?app_key=your_appkey_here&method=crossBorder.notifyValueAddedOrderOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 错误码 | `0` |
| `msg` | string | 异常信息 | `成功` |
| `data` | string | data | `data` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "data",
    "msg": "成功"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
