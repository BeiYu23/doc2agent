# iop.sellerOrderInfo

> 【商家】查看代发订单详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.sellerOrderInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/sellerOrderInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/1875 |
| 更新日期 | `2021-09-09` |

## 接口说明

- 文档书: 代发API（版本 V3.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `distr_order_id` | body | string | 是 | 代打订单号 | `77878786688878787` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/sellerOrderInfo?app_key=your_appkey_here&method=iop.sellerOrderInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `distr_order_detail` | object | 代发订单详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 代发订单不能为空（sub_code: isv.parameter-invalid:10000） | 请检查代发单号 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20000） | 重试 |
| `50002` | 业务处理失败 / 代发单不存在（sub_code: isv.business-failed:40000） | 代发单不存在 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:1000） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "distr_order_detail": {
      "after_sale_status": "2",
      "city": "北京",
      "city_id": "110000",
      "company_name": "shunfeng",
      "distr_cancel_reason": "订单已取消",
      "distr_order_id": "77878786688878787",
      "distr_status": "2",
      "distr_time": "1630484005",
      "district": "海淀区",
      "district_id": "110000",
      "exp_ship_time": "1630484005",
      "order_status": "2",
      "out_sku_id": "213412x",
      "pack_list": [
        {
          "company_code": "jd",
          "track_no": "1234"
        }
      ],
      "pay_time": "1630484005",
      "product_count": "2",
      "product_id": "77878786688878787",
      "product_name": "苹果",
      "product_price": "1000",
      "province": "北京",
      "province_id": "110000",
      "seller_words": "发货黑色",
      "serial_number_list": "[\"546443524543534\",\"646443524543534\"]",
      "ship_time": "1630484005",
      "shop_order_id": "77878786688878787",
      "sku_spec": "褐色",
      "street": "中关村",
      "street_id": "110000",
      "supplier_shop_id": "77977",
      "supplier_shop_name": "测试店铺名称",
      "tracking_no": "34545455"
    }
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "代发订单不能为空"
}
```

## 备注
