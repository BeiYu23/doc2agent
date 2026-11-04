# 删除售后地址策略

> address.delAftersaleStrategy — 删除售后地址策略

| 元信息 | 值 |
| --- | --- |
| 中文名 | 删除售后地址策略 |
| 文档地址 | `/docs/doudian/refund/refund-address-delAftersaleStrategy` |
| 接口 ID | `doudian.refund.address.delAftersaleStrategy` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/delAftersaleStrategy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6909 |
| 更新日期 | `2024-09-25` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `strategy_id` | body | string | 否 | 必填，售后地址策略。 | `AFS7418487171435053348` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/delAftersaleStrategy?app_key=your_appkey_here&method=address.delAftersaleStrategy&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请输入正确的参数（sub_code: isv.parameter-invalid:4000） | 按照返回的提示信息修改参数后重试。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:8001） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |

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
  "sub_code": "isv.parameter-invalid:4000",
  "sub_msg": "请输入正确的参数"
}
```

## 备注
