# iop.sellerCancleDistribute

> 【商家】取消分配代发订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.sellerCancleDistribute` |
| 中文名 | 【商家】取消分配代发订单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/sellerCancleDistribute` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/1876 |
| 更新日期 | `2021-09-09` |

## 接口说明

- 文档书: 代发API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `distr_order_ids` | body | array | 是 | 代打订单号 | `["34534534534534","34535345345345"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/sellerCancleDistribute?app_key=your_appkey_here&method=iop.sellerCancleDistribute&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `succ_distr_order_ids` | array | 操作成功的代打订单号 | `["4535353535","3453543534535"]` |
| `fail_distr_order_ids` | string | 操作失败的代打订单号 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 一次最多取消:100（sub_code: isv.business-failed:10000） | 请检查订单数量 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_distr_order_ids": {},
    "succ_distr_order_ids": "[\"4535353535\",\"3453543534535\"]"
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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "一次最多取消:100"
}
```

## 备注
