# btas.getOrderInspectionResult

> 商家_获取订单的质检结果（鉴定结论）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.getOrderInspectionResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/getOrderInspectionResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/573 |
| 更新日期 | `2021-06-07` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `0123456787` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/getOrderInspectionResult?app_key=your_appkey_here&method=btas.getOrderInspectionResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_id` | string | 父订单（店铺单）编号 | `4775168038676399798` |
| `product_order_id` | string | 商品单编号 | `4775168038676399798` |
| `order_code` | string | 订单码 | `0123456787` |
| `inspection_result` | string | 鉴定结果 | `1` |
| `certification_code` | string | 证书编号 | `XXXX-2021-03T617` |
| `detail` | string | 鉴定明细 | `{\"id\":\"20455\",\"region\":\"6\",\"order_id\":\"0\",\"type\":\"2\",\"zsbh\":\"COIC-2021-03T617\"}` |
| `inspection_comment` | string | 鉴定备注 | `表盘后镶钻` |
| `inspection_cost` | number | 鉴定费用 | `200` |
| `logistics_cost` | number | 物流费用 | `2000` |
| `inspection_time` | string | 鉴定结果时间戳（秒） | `1616679140` |
| `inspection_order_id` | string | 鉴定单ID | `GGEE12321` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 质检任务不存在，请确认（sub_code: isv.business-failed:4002） | 稍后重试 |
| `50002` | 业务处理失败 / 订单还未送检（sub_code: isv.business-failed:-1） | 先送检，完成质检在查看质检结果 |

## 响应示例

成功：

```json
{
  "data": {
    "certification_code": "XXXX-2021-03T617",
    "detail": "{\\\"id\\\":\\\"20455\\\",\\\"region\\\":\\\"6\\\",\\\"order_id\\\":\\\"0\\\",\\\"type\\\":\\\"2\\\",\\\"zsbh\\\":\\\"COIC-2021-03T617\\\"}",
    "inspection_comment": "表盘后镶钻",
    "inspection_cost": "200",
    "inspection_order_id": "GGEE12321",
    "inspection_result": "1",
    "inspection_time": "1616679140",
    "logistics_cost": "2000",
    "order_code": "0123456787",
    "order_id": "4775168038676399798",
    "product_order_id": "4775168038676399798"
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
  "sub_code": "isv.business-failed:4002",
  "sub_msg": "质检任务不存在，请确认"
}
```

## 备注
