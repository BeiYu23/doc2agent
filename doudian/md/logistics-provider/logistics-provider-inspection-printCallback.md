# inspection.printCallback

> qic外部系统打印回调

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.inspection.printCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/printCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8646 |
| 更新日期 | `2026-10-08` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `agencyId` | body | mixed | 否 | 质检机构 ID；QMS 仍需根据任务数据校验，不能只信任入参。 | `6` |
| `operatorPhone` | body | string | 否 | 映射为原打印回调的操作人信息；手机号映射失败不卡流程。 | `操作人手机号` |
| `operator_name` | body | string | 否 | 操作人姓名 | `操作人姓名` |
| `batchList` | body | array | 否 | 按批次执行，ngtc 确认同批次完成才会回调 | `` |
| `  └ printTime` | body | mixed | 否 | 打印时间戳 | `1790065409` |
| `  └ inspectionBatchId` | body | mixed | 否 | 质检批次号 | `123` |
| `  └ inspectionRecheckFinishTime` | body | mixed | 否 | 复核完成时间 | `1790065000` |
| `  └ status` | body | mixed | 否 | 打印状态，1-失败，2-成功 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/printCallback?app_key=your_appkey_here&method=inspection.printCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 结果编码 | `10000` |
| `msg` | string | 结果描述 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务异常（sub_code: isv.business-failed:500） | 排查 or重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "10000",
    "msg": "success"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:500",
  "sub_msg": "业务异常"
}
```

## 备注
