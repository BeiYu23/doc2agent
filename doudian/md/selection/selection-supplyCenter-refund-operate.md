# supplyCenter.refund.operate

> 退款驱动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.refund.operate` |
| 中文名 | 退款驱动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/refund/operate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/4818 |
| 更新日期 | `2023-11-03` |

## 接口说明

- 文档书: 精选货源API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_refund_infos` | body | array | 是 | 退款操作的子单号 | `` |
| `  └ reject_reason` | body | string | 否 | 退款拒绝原因 | `商品已经发货了` |
| `  └ close_reason` | body | string | 否 | 关单原因 | `支付取消` |
| `  └ pur_sku_order_id` | body | string | 是 | 精选货源子单号 | `123` |
| `  └ operation_type` | body | string | 是 | 操作类型0、发起售后 1、同意退款 2、同意退货 3、拒绝退款 4、售后成功 5、售后关闭 | `1` |
| `  └ address` | body | object | 否 | 地址信息 | `` |
| `    └ detail` | body | string | 否 | 详细地址 | `xx省xx市xx街道xx小区` |
| `    └ user_name` | body | string | 否 | 用户名称 | `张三` |
| `    └ mobile` | body | string | 否 | 手机号 | `17012341234` |
| `  └ aftersale_type` | body | number | 否 | 售后类型，发起售后时，需传入 1、售后仅退款 2、售前仅退款 3、申请退货退款 | `0` |
| `pur_order_id` | body | string | 是 | 精选货源单号 | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.refund.operate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

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
