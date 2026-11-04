# iop.orderInfo

> 【厂商】订单详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.orderInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/orderInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/678 |
| 更新日期 | `2024-06-25` |

## 接口说明

- 文档书: 代发API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | mixed | 是 | 代打店铺id | `343532434322232343243` |
| `distr_order_id` | body | string | 是 | 代打订单号 | `77878786688878787` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/orderInfo?app_key=your_appkey_here&method=iop.orderInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `distr_order_id` | string | 代打订单号 | `77878786688878787` |
| `user_id` | mixed | 代打店铺id | `55557775757756` |
| `user_name` | string | 代打店铺自定义名称 | `xxx店` |
| `seller_words` | string | 卖家备注 | `发xxx快递` |
| `distr_time` | mixed | 分配时间,秒 | `1625628558` |
| `distr_status` | mixed | 分配状态 0：未分配 1：已分配未回传；2已回传; 3已取消 | `1` |
| `product_name` | string | 商品名称 | `衣服` |
| `product_count` | mixed | 商品数量 | `2` |
| `product_id` | string | 商品id | `1142351234` |
| `product_price` | mixed | 商品价格 | `990` |
| `sku_spec` | string | 规格 | `绿色/小` |
| `out_sku_id` | string | 商家配置的sku编码 | `A11` |
| `receiver_id` | string | 收件人姓名+电话+详细地址相同,receiver_id字段相同 | `4239E33B82F201A3D73D8DA2DDA21AD4` |
| `province` | string | 省 | `上海市` |
| `city` | string | 市 | `上海市` |
| `district` | string | 区 | `长宁区` |
| `street` | string | 街道 | `中关村` |
| `province_id` | string | 省ID | `110000` |
| `city_id` | string | 市ID | `110000` |
| `district_id` | string | 区ID | `110000` |
| `street_id` | string | 街道IID | `110000` |
| `distr_cancel_reason` | string | 代发取消原因 | `订单已取消` |
| `buyer_words` | string | 买家备注 | `买家备注信息` |
| `distr_order_aftersale_status` | mixed | 代发单售后状态，1-无售后或售后关闭，2-有售后 | `1` |
| `exp_ship_time` | mixed | 预期发货时间 | `1637224278` |
| `ship_time` | mixed | 发货时间 | `1637224278` |
| `serial_number_list` | array | 序列号 | `["546443524543534","646443524543534"]` |
| `pack_list` | array | 物流信息 | `` |
| `order_tag` | string | 标签信息 | `{    "shop_optional_express_info": "{\"ServiceName\":\"顺丰速运\",\"ServiceCode\":\"shunfeng\",\"ExpressCompanys\":[{\"ExpressCompanyCode\":\"shunfeng\",\"ExpressCompany\":\"顺丰速运\"}],\"Amount\":200}" }` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单号不存在（sub_code: isv.parameter-invalid:40000） | 检查订单号是否已取消分配 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:88888） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 10005:系统繁忙，请稍后重试（sub_code: isv.business-failed:10005） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 1000:系统繁忙，请稍后重试（sub_code: isv.business-failed:1000） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "buyer_words": "买家备注信息",
    "city": "上海市",
    "city_id": "110000",
    "distr_cancel_reason": "订单已取消",
    "distr_order_aftersale_status": "1",
    "distr_order_id": "77878786688878787",
    "distr_status": "1",
    "distr_time": "1625628558",
    "district": "长宁区",
    "district_id": "110000",
    "exp_ship_time": "1637224278",
    "order_tag": {},
    "out_sku_id": "A11",
    "pack_list": [
      {
        "company_code": "jd",
        "deliver_id": "77878786688878782",
        "track_no": "123456"
      }
    ],
    "product_count": "2",
    "product_id": "1142351234",
    "product_name": "衣服",
    "product_price": "990",
    "province": "上海市",
    "province_id": "110000",
    "receiver_id": "4239E33B82F201A3D73D8DA2DDA21AD4",
    "seller_words": "发xxx快递",
    "serial_number_list": "[\"546443524543534\",\"646443524543534\"]",
    "ship_time": "1637224278",
    "sku_spec": "绿色/小",
    "street": "中关村",
    "street_id": "110000",
    "user_id": "55557775757756",
    "user_name": "xxx店"
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
  "sub_code": "isv.parameter-invalid:40000",
  "sub_msg": "订单号不存在"
}
```

## 备注
