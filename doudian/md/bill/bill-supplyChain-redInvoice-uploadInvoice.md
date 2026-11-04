# supplyChain.redInvoice.uploadInvoice

> 上传红票

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.supplyChain.redInvoice.uploadInvoice` |
| 中文名 | 上传红票 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/8000 |
| 更新日期 | `2026-04-23` |

## 接口说明

- 文档书: 账单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `applyNo` | body | string | 是 | 退票申请单号 | `IAO7585313919070241123` |
| `refundInfo` | body | object | 是 | 提交信息 | `` |
| `  └ invoiceDataList` | body | array | 是 | 选择的发票列表 | `` |
| `    └ amountStr` | body | string | 否 | 发票金额 | `10186` |
| `    └ invoiceCode` | body | string | 否 | 发票代码 | `60005340` |
| `    └ taxAmountStr` | body | string | 否 | 发票税额 | `1171` |
| `    └ createTime` | body | mixed | 否 | 开票时间 | `1765402431` |
| `    └ invoiceNo` | body | string | 是 | 发票号码 | `25317000003164324417` |
| `    └ isChoose` | body | boolean | 是 | 发票是否选择 | `true` |
| `    └ invoiceAuthed` | body | boolean | 否 | 发票是否认证 | `false` |
| `    └ oApplyNo` | body | string | 否 | oA申请单号 | `G2025121060005340` |
| `  └ isRedReversal` | body | boolean | 是 | 是否部分红冲 | `false` |
| `  └ invoiceAttachment` | body | array | 否 | 发票地址 | `` |
| `    └ invoiceCode` | body | string | 是 | 发票号码 | `25317000003331047603` |
| `    └ externalUrl` | body | string | 是 | 素材uri，仅支持pdf和ofd格式，获取方式见https://bytedance.larkoffice.com/docx/doxcnyCpq3C9gik15T2dtKK0Tlc | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `    └ amount` | body | string | 是 | 发票金额 | `-10186` |
| `  └ applyReason` | body | string | 是 | - 退票原因  1：开票有误，2：服务终止，3：销货退回，4：销售折让 | `4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.redInvoice.uploadInvoice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 错误码，"0"代表请求成功 | `0` |
| `msg` | string | 错误码说明 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常:%s（sub_code: isp.service-error:1001） | 重试或联系内部人员 |
| `40004` | 非法的参数 / 参数异常:%s（sub_code: isv.parameter-invalid:1002） | 检查参数 |
| `50002` | 业务处理失败 / 当前状态不支持当前指令（sub_code: isv.business-failed:1003） | 检查当前流程操作是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1001",
  "sub_msg": "系统异常:%s"
}
```

## 备注
