# btas.sellerGetPowerCode

> 商家_电子面单取号

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.sellerGetPowerCode` |
| 中文名 | 商家_电子面单取号 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sellerGetPowerCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2944 |
| 更新日期 | `2024-11-19` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `43534113` |
| `sc_receipt_courier_type` | body | mixed | 是 | 质检机构物流编号。1-顺丰 | `1` |
| `sc_receipt_order_insurance_cost` | body | mixed | 是 | 报价金额（分） | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/sellerGetPowerCode?app_key=your_appkey_here&method=btas.sellerGetPowerCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `power_order_track_no` | string | 物流单号 | `SF342341333111` |
| `s_c_receipt_courier_code_count` | mixed | 取号次数，当前限制为4 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "power_order_track_no": "SF342341333111",
    "s_c_receipt_courier_code_count": "1"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
