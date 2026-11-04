# retail.afterSale.applyNegotiate

> 商家发起协商

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-refund.retail.afterSale.applyNegotiate` |
| 中文名 | 商家发起协商 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1548/6898 |
| 更新日期 | `2024-09-23` |

## 接口说明

- 文档书: 售后管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pre_after_sale_reason_code` | body | mixed | 是 | 修改的售后原因，可选枚举及含义参考YOUR_SECRET_KEY接口返回值 | `23` |
| `pre_refund_amount` | body | mixed | 是 | 修改的退款金额，最大可选金额参考YOUR_SECRET_KEY接口返回值 | `1420` |
| `pre_after_sale_item_count` | body | mixed | 是 | 修改的售后数量，最大可选数量参考YOUR_SECRET_KEY接口返回值 | `1` |
| `im_negotiate_info` | body | object | 否 | im消息 | `` |
| `  └ im_text` | body | string | 否 | im对话内容 | `测试文案` |
| `after_sale_id` | body | mixed | 是 | 售后单ID | `146602997871474402` |
| `negotiate_time` | body | mixed | 否 | 协商时长，单位秒，商家主动发起协商场景下不需要传 | `0` |
| `negotiate_scene` | body | mixed | 否 | 协商场景，可选枚举及含义参考YOUR_SECRET_KEY接口返回值 | `1` |
| `pre_after_sale_type` | body | mixed | 是 | 修改的售后类型，可选枚举及含义参考YOUR_SECRET_KEY接口返回值 | `1` |
| `pre_package_status` | body | mixed | 是 | 修改的货物状态，0未收到货，1已收到货，可选枚举及含义参考YOUR_SECRET_KEY接口返回值 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=retail.afterSale.applyNegotiate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `negotiate_deadline` | mixed | 协商截止时间，秒级时间戳 | `1726671931` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常-可重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |
| `40004` | 非法的参数 / 售后金额校验未通过（sub_code: isv.parameter-invalid:5100504） | 请按照错误文案输入正确的售后金额 |
| `40004` | 非法的参数 / 货物状态校验未通过（sub_code: isv.parameter-invalid:5100502） | 请按照错误文案输入正确的货物状态 |
| `40004` | 非法的参数 / 售后原因校验未通过（sub_code: isv.parameter-invalid:5100503） | 请按照错误文案输入正确的售后原因 |
| `40004` | 非法的参数 / 售后件数校验未通过（sub_code: isv.parameter-invalid:5100505） | 请按照错误文案输入正确的售后件数 |
| `40004` | 非法的参数 / 售后方式校验未通过（sub_code: isv.parameter-invalid:5100501） | 请按照错误文案输入正确的售后方式 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入必填参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常-不可重试的错误（sub_code: isv.business-failed:5000001） | 业务处理失败 |

## 响应示例

成功：

```json
{
  "data": {
    "negotiate_deadline": "1726671931"
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
  "sub_code": "isp.service-error:5100002",
  "sub_msg": "系统异常-可重试"
}
```

## 备注
