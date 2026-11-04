# 信息推送

> logistics.courierStation.updateTerminalOrder — 信息推送

| 元信息 | 值 |
| --- | --- |
| 中文名 | 信息推送 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-courierStation-updateTerminalOrder` |
| 接口 ID | `doudian.logistics-provider.logistics.courierStation.updateTerminalOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2935 |
| 更新日期 | `2026-09-16` |

## 接口说明

- 文档书: 物流商API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bizType` | body | string | 是 | 业务类型； 支持‘\|’分割，批量传入多个类型，枚举： POST_WEIGHT_INFO--核重核价 POST_WAYBILL_INFO--运单号 POST_COLLECT_STATUS--揽收状态 | `POST_WEIGHT_INFO\|POST_WEIGHT_INFO` |
| `orderId` | body | string | 是 | 订单号 | `LFO12345678904567` |
| `operationTime` | body | string | 是 | 操作时间（格式：yyyy-MM-dd HH:mm:ss，24小时制） | `2023-02-03 00:00:00` |
| `postInfo` | body | object | 否 | 推送信息 | `` |
| `  └ express` | body | string | 否 | 物流商编码 | `zhongtong` |
| `  └ weightInfo` | body | object | 否 | 核重核价信息 | `` |
| `    └ packageFee` | body | mixed | 否 | 包装费（单位：分） | `150` |
| `    └ length` | body | string | 否 | 长度 | `100` |
| `    └ certificate_photos` | body | array | 否 | 核重核价凭证图片url列表 | `["https://xxx.jpg","https://xxx2.jepg"]` |
| `    └ width` | body | string | 否 | 宽度 | `100` |
| `    └ is_master_and_child` | body | boolean | 否 | 是否子母单 | `false` |
| `    └ insuredFee` | body | mixed | 否 | 保价费（单位：分） | `5000` |
| `    └ chargedWeight` | body | mixed | 否 | 包裹计费重量（单位：克） | `1000` |
| `    └ child_package_volume_list` | body | array | 否 | 子单体积数据 | `` |
| `      └ height` | body | mixed | 否 | 包裹高度 | `100` |
| `      └ length` | body | mixed | 否 | 包裹长度 | `100` |
| `      └ width` | body | mixed | 否 | 包裹宽度 | `100` |
| `    └ chargedType` | body | mixed | 否 | 计费类型； 枚举：1--重量，2--体积 | `2` |
| `    └ sumFee` | body | mixed | 否 | 总金额（单位：分） | `800` |
| `    └ actualWeight` | body | mixed | 否 | 包裹实际重量（单位：克） | `2000` |
| `    └ height` | body | string | 否 | 高度 | `100` |
| `  └ waybillCode` | body | string | 否 | 运单号 | `71234658` |
| `partnerCode` | body | string | 是 | 服务商编码 | `yuantong` |
| `postCode` | body | string | 否 | 驿站编码 | `xx` |
| `postName` | body | string | 否 | 驿站名称 | `xxx` |
| `brandCode` | body | string | 是 | 品牌编码 | `mamayizhan` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.courierStation.updateTerminalOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `errCode` | string | 失败原因编码（处理成功默认回传“0”） | `0` |
| `errReason` | string | 失败原因描述 | `处理成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10001） | 修改请求参数 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10002） | 接口重试 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10003） | 联系开发人员 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10101） | 订单不存在 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10102） | 订单已取消 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10106） | 订单当前状态不允许核重核价 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10107） | 订单当前状态不允许揽收 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10108） | 不支持重复核重核价 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10109） | 不支持重复揽收 |
| `50002` | 业务处理失败 / 11017:数据库并发（sub_code: isv.business-failed:11017） | 11017:数据库并发 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10110） | 重量异常，重新输入重量信息并补充核重凭证 |

## 响应示例

成功：

```json
{
  "data": {
    "errCode": "0",
    "errReason": "处理成功"
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
  "sub_code": "isp.service-error:10001",
  "sub_msg": "-"
}
```

## 备注
