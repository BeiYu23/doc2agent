# 商家确认是否收到换货

> afterSale.buyerExchangeConfirm — 商家确认是否收到换货

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家确认是否收到换货 |
| 文档地址 | `/docs/doudian/refund/refund-afterSale-buyerExchangeConfirm` |
| 接口 ID | `doudian.refund.afterSale.buyerExchangeConfirm` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/buyerExchangeConfirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/768 |
| 更新日期 | `2021-08-03` |

## 接口说明

- 文档书: 售后退款API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 可以从/afterSale/refundProcessDetail接口或者消息监听获取 | `123123123123123` |
| `is_reject` | body | boolean | 是 | 处理方式： false：确认仓库收到退回货货物并二次发货（或直接退款） true：拒绝 | `true` |
| `action` | body | string | 否 | s_reject为false时，必填，用于指定换货操作行为；换货动作： refund_agree ： 同意换货转退款 exchange_agree：同意换货并发货 | `refund_agree` |
| `comment` | body | string | 否 | is_reject = true 时需要选择拒绝原因；具体各个可选值对应的拒绝原因见下表 | `1` |
| `evidence` | body | array | 否 | 凭证图片，只能传一张 | `["http://pic/pic.jpeg"]` |
| `logistics_code` | body | string | 否 | is_reject = false时需要上传物流单号 | `123` |
| `company_code` | body | string | 否 | is_reject = false时需要上传物流公司编号 ，如圆通为yuantong | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/buyerExchangeConfirm?app_key=your_appkey_here&method=afterSale.buyerExchangeConfirm&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 此订单状态已经发生变化，请刷新（sub_code: isv.parameter-invalid:10007） | 检查售后单状态 |
| `50002` | 业务处理失败 / 参数错误，请修改后重试（sub_code: isv.business-failed:10002） | 检查售后单状态 |
| `20000` | 服务不可用 / 系统超时，请重试（sub_code: isp.service-error:10001） | 检查并重试 |
| `50002` | 业务处理失败 / 存在非本店铺订单，该操作被禁止（sub_code: isv.business-failed:10004） | 检查参数后重试 |

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
  "sub_code": "isv.parameter-invalid:10007",
  "sub_msg": "此订单状态已经发生变化，请刷新"
}
```

## 备注
