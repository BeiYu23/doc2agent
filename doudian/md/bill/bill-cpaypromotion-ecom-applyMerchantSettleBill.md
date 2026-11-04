# 通过url方式

> cpaypromotion.ecom.applyMerchantSettleBill — 1、通过url方式，下载文件生成结算账单下单接口，调用该接口生成一个download_id ，通过返回的download_id调用【YOUR_SECRET_KEY】查询下载url文件链接。如果申

| 元信息 | 值 |
| --- | --- |
| 中文名 | 通过url方式 |
| 文档地址 | `/docs/doudian/bill/bill-cpaypromotion-ecom-applyMerchantSettleBill` |
| 接口 ID | `doudian.bill.cpaypromotion.ecom.applyMerchantSettleBill` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/7722 |
| 更新日期 | `2025-08-26` |

## 接口说明

- 文档书: 账单API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bill_start_time` | body | string | 是 | 账单开始时间，格式：yyyyMMdd | `20250819` |
| `bill_end_time` | body | string | 是 | 账单结束时间，格式：yyyyMMdd | `20250819` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyConsign?app_key=your_appkey_here&method=supplyChain.supplyConsign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `download_id` | string | 下载id，后续商家需要通过这个下载id获取文件下载链接 | `AID202508192022172663404076` |
| `biz_base_response` | object | 响应体 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 该商家不支持下载账单文件（sub_code: isv.parameter-invalid:CF93301121） | 传入有下载账单权限的商家id |
| `40004` | 非法的参数 / 申请时间段内无账单（sub_code: isv.parameter-invalid:CF93301122） | 修改账单下载时间段 |
| `40004` | 非法的参数 / 只支持下载30天内的账单（sub_code: isv.parameter-invalid:CF93301127） | 修改账单下载时间段，不能超过30天 |
| `40004` | 非法的参数 / 不能申请未来时间的账单（sub_code: isv.parameter-invalid:CF93301128） | 修改账单下载时间段，不能申请未来时间的账单 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:CF93301001） | 根据接口文档要求传入参数 |
| `40004` | 非法的参数 / 时间格式不合规（sub_code: isv.parameter-invalid:CF93301006） | 根据接口文档要求符合规定的时间 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isv.parameter-invalid:CF93301121",
  "sub_msg": "该商家不支持下载账单文件"
}
```

## 备注
