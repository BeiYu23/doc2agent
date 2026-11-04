# afterSale.ApplyMarketAfterSale

> 申请缺重/缺货

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.afterSale.ApplyMarketAfterSale` |
| 中文名 | 申请缺重/缺货 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/ApplyMarketAfterSale` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2402 |
| 更新日期 | `2025-11-26` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_order_id` | body | string | 是 | 子订单号，缺件整单退场景使用after_sale_reason=2+ sku_order_id即可 | `4243564562342144` |
| `miss_gram` | body | mixed | 否 | 缺重克数，单位 毫克；当after_sale_reason =1时缺重场景，该字段必传。其他场景无需使用。当miss_gram有值。①refund_amount不传时，平台会根据重量计算应退给用户金额。②refund_amount传入时退款金额以商家传入的金额为准，最多不会超过该订单剩余可退款金额 | `100` |
| `refund_amount` | body | mixed | 否 | 退款金额，缺重场景下有效，单位分；①refund_amount不传时，平台会根据重量计算应退给用户金额。②refund_amount传入时退款金额以商家传入的金额为准，最多不会超过该订单剩余可退款金额 | `100` |
| `item_count` | body | mixed | 否 | 1. 件数，缺件部分退场景使用，after_sale_reason=2时使用，传入要部分退的数量，平台会自动根据件数计算金额进行退款。缺件整单退使用after_sale_reason=2+ sku_order_id即可 2. 按件报缺也需要传入 | `12` |
| `after_sale_reason` | body | mixed | 是 | 售后原因枚举，1=缺重；2=缺件； 3=用户拒收，支持按件数退，金额由抖音计算 | `1` |
| `store_id` | body | mixed | 否 | 门店ID，传了就做检验，不传默认通过，由isv自行保证权限 | `1111` |
| `miss_gram_type` | body | mixed | 否 | 缺重类型：0:整体报缺 1:按件报缺 | `1` |
| `miss_gram_detail` | body | array | 否 | 按件报缺 | `` |
| `  └ refund_amount` | body | mixed | 否 | 退款金额，单位分。传入100为1元 | `100` |
| `  └ miss_gram` | body | mixed | 否 | 缺重克数，单位 毫克。传入100000为100克 | `100000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/ApplyMarketAfterSale?app_key=your_appkey_here&method=afterSale.ApplyMarketAfterSale&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `after_sale_id` | string | 售后ID | `7054483962693042445` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 12000:订单售后申请总次数已达1次，无法再次发起（sub_code: isv.business-failed:12000） | 无法重试 |
| `50002` | 业务处理失败 / 10000:系统错误，请重试（sub_code: isv.business-failed:10000） | 可重试解决 |
| `50002` | 业务处理失败 / 12001:当前场景不可发起！请确认订单发货状态！（sub_code: isv.business-failed:12001） | 12001:当前场景不可发起！请确认订单发货状态！ |
| `50002` | 业务处理失败 / 11000:缺重场景下 RefundAmount 和 MissGram 不得为空（sub_code: isv.business-failed:11000） | 11000:缺重场景下 RefundAmount 和 MissGram 不得为空 |

## 响应示例

成功：

```json
{
  "data": {
    "after_sale_id": "7054483962693042445"
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
  "sub_code": "isv.business-failed:12000",
  "sub_msg": "12000:订单售后申请总次数已达1次，无法再次发起"
}
```

## 备注
