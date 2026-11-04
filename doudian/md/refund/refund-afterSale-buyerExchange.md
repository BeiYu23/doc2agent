# afterSale.buyerExchange

> 商家处理换货请求接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.buyerExchange` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/buyerExchange` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/769 |
| 更新日期 | `2021-08-03` |

## 接口说明

- 文档书: 售后退款API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 售后ID | `7028908275186158347` |
| `is_reject` | body | boolean | 是 | 是否拒绝 | `true` |
| `sms_id` | body | number | 否 | 短信模板ID | `123123` |
| `comment` | body | string | 否 | 商家留言 | `同意` |
| `evidence` | body | array | 否 | 商家凭证 | `""` |
| `address_id` | body | number | 否 | 商家选择的换货地址 | `123` |
| `remark` | body | string | 否 | 商家备注 | `好吧，那就换吧` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/buyerExchange?app_key=your_appkey_here&method=afterSale.buyerExchange&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 此订单状态已经发生变化，请刷新（sub_code: isv.business-failed:10007） | 检查售后单状态 |
| `50002` | 业务处理失败 / 售后类型无法处理（sub_code: isv.business-failed:10002） | 检查售后单状态 |
| `20000` | 服务不可用 / 服务器繁忙，请刷新后重试（sub_code: isp.service-error:10001） | 检查后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10007",
  "sub_msg": "此订单状态已经发生变化，请刷新"
}
```

## 备注
