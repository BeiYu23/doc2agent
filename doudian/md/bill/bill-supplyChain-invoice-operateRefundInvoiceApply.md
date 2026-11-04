# supplyChain.invoice.operateRefundInvoiceApply

> 红字确认单上传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.supplyChain.invoice.operateRefundInvoiceApply` |
| 中文名 | 红字确认单上传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/7999 |
| 更新日期 | `2026-04-23` |

## 接口说明

- 文档书: 账单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `applyNo` | body | string | 是 | 退票申请单号 | `IAO7585313919070241123` |
| `refundInfo` | body | object | 是 | 提交信息 | `` |
| `  └ applyReason` | body | string | 是 | 申请原因 1：开票有误，2：服务终止，3：销货退回，4：销售折让 | `3` |
| `  └ redInfoAttachment` | body | array | 是 | 红字信息列表 | `` |
| `    └ redInfoWordNo` | body | string | 是 | 红字信息表号码 | `44430426041004976777` |
| `    └ amount` | body | string | 否 | 红字金额 | `-2478.01` |
| `    └ url` | body | string | 否 | 红字信息表url | `url` |
| `  └ isRedReversal` | body | boolean | 是 | 是否部分红冲 false | `false` |
| `  └ invoiceDataList` | body | array | 是 | 选择的发票列表 | `` |
| `    └ invoiceNo` | body | string | 是 | 发票号码 | `25442000000540330123` |
| `    └ invoice_status` | body | string | 否 | 发票状态 | `0` |
| `    └ taxAmountStr` | body | string | 否 | 发票税额 | `23944.67` |
| `    └ invoiceAuthed` | body | boolean | 否 | 发票是否认证 | `true` |
| `    └ createTime` | body | mixed | 否 | 开票时间 | `1750888817` |
| `    └ amountStr` | body | string | 否 | 发票金额 | `1248.67` |
| `    └ invoiceCode` | body | string | 否 | 发票代码 | `11` |
| `    └ oApplyNo` | body | string | 否 | oA申请单号 | `11` |
| `    └ isChoose` | body | boolean | 是 | 发票是否选择 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.invoice.operateRefundInvoiceApply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
