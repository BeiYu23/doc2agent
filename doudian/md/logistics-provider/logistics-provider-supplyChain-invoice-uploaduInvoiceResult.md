# 上传开票结果

> supplyChain.invoice.uploaduInvoiceResult — 上传开票结果。
该接口仅上门安装服务商使用。
商家给消费者上传发票文件用/order/invoiceUpload接口。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上传开票结果 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-supplyChain-invoice-uploaduInvoiceResult` |
| 接口 ID | `doudian.logistics-provider.supplyChain.invoice.uploaduInvoiceResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6939 |
| 更新日期 | `2024-10-17` |

## 接口说明

- 文档书: 物流商API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `manual_invoice` | body | object | 是 | 手动上传发票 | `` |
| `  └ invoice_scene` | body | string | 是 | 开票场景(1:蓝票) | `1` |
| `  └ manual_invoice_info` | body | array | 是 | 发票列表(文件数量大于0小于等于3) | `` |
| `    └ file_url` | body | string | 是 | 素材uri，仅支持pdf和ofd格式，获取方式见https://bytedance.larkoffice.com/docx/doxcnyCpq3C9gik15T2dtKK0Tlc | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `    └ file_name` | body | string | 是 | 文件名称 | `invoice.pdf` |
| `apply_no` | body | string | 是 | 开票申请单号 | `IAO7366832755336380690` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/infoCallBack?app_key=your_appkey_here&method=power.infoCallBack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_code` | string | 错误码，"000000"代表请求成功，"200007"代表已经写入成功无需重复写入，其他编码代表请求失败 | `000000` |
| `ret_msg` | string | 错误码说明 | `处理成功` |

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
