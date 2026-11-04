# btas.sc.listOrderCodeByPickupCode

> 根据商家自提码查询订单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.sc.listOrderCodeByPickupCode` |
| 中文名 | 根据商家自提码查询订单信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/listOrderCodeByPickupCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2940 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pickup_code` | body | string | 是 | 商家自提码，由商家在抖店后台自行取的 | `0324234` |
| `sc_id` | body | mixed | 是 | 质检机构ID | `02` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/sc/listOrderCodeByPickupCode?app_key=your_appkey_here&method=btas.sc.listOrderCodeByPickupCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pickup_code` | string | 自提码 | `0101023` |
| `order_list` | array | 订单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "order_list": [
      {
        "extra_properties": "[{\"Name\":\"颜色\",\"Value\":\"蓝宝石\"}]",
        "inspection_type": "1",
        "order_code": "2343531",
        "product_img": "http://baidu.com",
        "product_name": "Iphone 12 Pro",
        "product_price": "700000"
      }
    ],
    "pickup_code": "0101023"
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
