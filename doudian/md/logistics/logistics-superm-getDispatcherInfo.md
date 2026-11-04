# superm.getDispatcherInfo

> 运力呼叫询价/取消呼叫询价（正向）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.superm.getDispatcherInfo` |
| 中文名 | 运力呼叫询价/取消呼叫询价（正向 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/getDispatcherInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2740 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店ID | `111140954781` |
| `shop_order_id` | body | string | 是 | 订单ID | `4991349131563755389` |
| `dispatcher_fee_type` | body | string | 是 | 运力费用类型 1: 呼叫运力费用，2:取消运力费用 | `1` |
| `insurance_amount` | body | number | 否 | 保价金额，单位：分 | `1000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/materialsProductsSearch?app_key=your_appkey_here&method=alliance.materialsProductsSearch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `dispatcher_fee` | number | 运力费用，单位：分 | `1000` |
| `insurance_fee` | number | 保价费用，单位：分 | `1000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:1000001） | 参数非法 |
| `40002` | 缺少必选参数 / 店铺ID不能为空（sub_code: isv.missing-parameter:40011） | 店铺ID不能为空 |
| `40002` | 缺少必选参数 / 门店ID不能为空（sub_code: isv.missing-parameter:40012） | 门店ID不能为空 |
| `40002` | 缺少必选参数 / 订单不能为空（sub_code: isv.missing-parameter:40013） | 订单不能为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20111） | 订单查询失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20112） | 门店信息获取失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20113） | 执行单不存在 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20114） | 流水号为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20200） | 履约内部rpc调用失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20211） | 调用履约呼叫运力失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20212） | deliverId生成失败,原错误码505 |
| `50002` | 业务处理失败 / 非小时达订单不允许使用呼叫运力（sub_code: isv.business-failed:50110） | 非小时达订单不允许使用呼叫运力 |
| `50002` | 业务处理失败 / 未开通平台运力服务，无法使用。（sub_code: isv.business-failed:50111） | 未开通平台运力服务，无法使用。 |
| `50002` | 业务处理失败 / 非本店铺订单，呼叫运力失败（sub_code: isv.business-failed:50112） | 非本店铺订单，呼叫运力失败 |
| `50002` | 业务处理失败 / 发货订单包含非本门店订单，请重试（sub_code: isv.business-failed:50113） | 发货订单包含非本门店订单，请重试 |
| `50002` | 业务处理失败 / store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:50114） | store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50211） | 订单信息异常 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:50216） | 收件人信息解析失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20214） | 保价服务失败 |
| `50002` | 业务处理失败 / 非本店铺订单，禁止操作（sub_code: isv.business-failed:50102） | 非本店铺订单，禁止操作 |
| `50002` | 业务处理失败 / 请输入正确的费用信息（sub_code: isv.business-failed:700015） | 请输入正确的费用信息 |
| `50002` | 业务处理失败 / 120051:未开通平台运力服务（sub_code: isv.business-failed:120051） | 120051:未开通平台运力服务 |

## 响应示例

成功：

```json
{
  "data": {
    "products": [
      {
        "activity_id": "1",
        "available_coupons": [
          {
            "apply_end_time": "2016-01-01 13:00:00",
            "apply_start_time": "2016-01-01 12:00:00",
            "coupon_type": "1",
            "discount_desc": "满20减1",
            "type_desc": "平台券",
            "use_end_time": "2016-01-01 13:00:00",
            "use_start_time": "2016-01-01 12:00:00",
            "valid_period": "3600",
            "validity_type": "1"
          }
        ],
        "cos_fee": "1",
        "cos_ratio": "10",
        "coupon_price": "92",
        "cover": "https://sf1-ttcdn-tos.pstatp.com/img/temai/Fpt8famR3twTGYz09e25nz5PbTRuwww800-800~1125x1125_q50.webp",
        "detail_url": "https://haohuo.jinritemai.com/views/product/item2?id=3400312511185213726",
        "first_cid": "1206",
        "in_stock": "1",
        "limit_min_sale": "false",
        "post_free": "true",
        "presell_type": "0",
        "price": "100",
        "product_id": "3400312511185213726",
        "sales": "1234",
        "second_cid": "1402",
        "sharable": "true",
        "shop_id": "2232",
        "shop_name": "maggie测试小铺",
        "third_cid": "2634",
        "title": "测试商品"
      }
    ],
    "total": "1000"
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
  "sub_code": "isv.parameter-invalid:1000001",
  "sub_msg": "参数非法"
}
```

## 备注
