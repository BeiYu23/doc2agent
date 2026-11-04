# 上传蓝票

> supplyChain.blueInvoice.uploadInvoice — 上传蓝票

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上传蓝票 |
| 文档地址 | `/docs/doudian/bill/bill-supplyChain-blueInvoice-uploadInvoice` |
| 接口 ID | `doudian.bill.supplyChain.blueInvoice.uploadInvoice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/8001 |
| 更新日期 | `2026-04-23` |

## 接口说明

- 文档书: 账单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `paymentNo` | body | string | 是 | 付款单号（业务身份标识） | `PF47620251016123123` |
| `executeCommand` | body | object | 是 | 执行命令对象（封装发票上传核心参数） | `` |
| `  └ extData` | body | object | 是 | 发票列表封装结构体 | `` |
| `    └ invoiceListV2` | body | object | 是 | 发票列表封装结构体 | `` |
| `      └ invoices` | body | array | 是 | 发票明细数组 | `` |
| `        └ invoiceTime` | body | string | 否 | 2026-01-01 | `发票日期` |
| `        └ externalUrl` | body | string | 是 | 素材uri，仅支持pdf和ofd格式，获取方式见https://bytedance.larkoffice.com/docx/doxcnyCpq3C9gik15T2dtKK0Tlc | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `        └ amount` | body | mixed | 是 | 发票金额 | `65355` |
| `        └ invoiceNo` | body | string | 是 | 发票单号 | `PF23520990105001111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.blueInvoice.uploadInvoice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 错误码，"0"代表请求成功 | `0` |
| `msg` | string | 错误码说明 | `SUCCESS` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常:%s（sub_code: isp.service-error:1001） | 重试或联系内部人员 |
| `40004` | 非法的参数 / 参数异常:%s（sub_code: isv.parameter-invalid:1002） | 检查必填参数 |
| `50002` | 业务处理失败 / 当前状态不支持当前指令（sub_code: isv.business-failed:1003） | 检查当前流程操作是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "SUCCESS"
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
