# 即时零售呼叫平台运力

> instantShopping.callDeliveryPlatform — 即时零售呼叫平台运力

| 元信息 | 值 |
| --- | --- |
| 中文名 | 即时零售呼叫平台运力 |
| 文档地址 | `/docs/doudian/logistics/logistics-instantShopping-callDeliveryPlatform` |
| 接口 ID | `doudian.logistics.instantShopping.callDeliveryPlatform` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/7042 |
| 更新日期 | `2025-09-09` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 抖音电商shop order单id | `6917539978356459031` |
| `store_id` | body | mixed | 是 | 门店ID | `1111409547` |
| `verify_code_type` | body | mixed | 否 | 是否需要取件码（0=不需要，1=需要） | `0/1` |
| `serial_number_list` | body | string | 否 | 序列码列表，如果包含有多个序列码，请用"_"英文下划线分割（属于数码手机类目的商品订单才需要传序列码。） | `353245234` |
| `need_receiver_code` | body | boolean | 否 | 是否需要收件码；true：需要；false：不需要 | `true` |
| `sku_trace_info_list` | body | array | 否 | sku单的医疗溯源码信息; | `` |
| `  └ sku_order_id` | body | string | 否 | 对应sku单id | `4945338777763599988` |
| `  └ batch_and_trace_code_list` | body | array | 否 | 批次+溯源码list（设计为list是可能有多个item单） | `` |
| `    └ batch_code` | body | string | 否 | 批次code | `12345` |
| `    └ trace_code` | body | string | 否 | 溯源码code | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.callDeliveryPlatform&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `delivery_distance` | mixed | 订单配送距离，单位米 | `3200` |
| `delivery_fee` | mixed | 订单配送价格，单位分 | `100` |
| `pickup_goods_code` | string | 四到六位验证码 | `2412` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:310000） | 参数非法，请检查传入的参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:50029） | 参数非法，请检查传入参数 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:700024） | 系统繁忙，请稍后重试 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:1000001） | 参数非法 |
| `40002` | 缺少必选参数 / 订单不能为空（sub_code: isv.missing-parameter:40013） | 订单不能为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20111） | 订单查询失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20112） | 门店信息获取失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20113） | 执行单不存在 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20114） | 流水号为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20200） | 履约查询超时 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20211） | 履约呼叫运力失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20212） | 履约生成deliverId失败 |
| `50002` | 业务处理失败 / 非小时达订单不允许使用呼叫运力（sub_code: isv.business-failed:50110） | 非小时达订单不允许使用呼叫运力 |
| `50002` | 业务处理失败 / 未开通平台运力服务，无法使用。（sub_code: isv.business-failed:50111） | 未开通平台运力服务，无法使用。 |
| `50002` | 业务处理失败 / 非本店铺订单，呼叫运力失败（sub_code: isv.business-failed:50112） | 非本店铺订单，呼叫运力失败 |
| `50002` | 业务处理失败 / 发货订单包含非本门店订单，请重试（sub_code: isv.business-failed:50113） | 发货订单包含非本门店订单，请重试 |
| `50002` | 业务处理失败 / store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:50114） | store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50211） | 运费获取失败，请重新获取。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:50216） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 超出配送范围（sub_code: isv.business-failed:50217） | 超出配送范围 |
| `50002` | 业务处理失败 / 不在站点营业时间（sub_code: isv.business-failed:50218） | 不在站点营业时间 |
| `50002` | 业务处理失败 / 未开通配送服务（sub_code: isv.business-failed:50219） | 未开通配送服务 |
| `50002` | 业务处理失败 / 运力紧张无法接单（sub_code: isv.business-failed:50220） | 运力紧张无法接单 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_distance": "3200",
    "delivery_fee": "100",
    "pickup_goods_code": "2412"
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
  "sub_code": "isv.parameter-invalid:310000",
  "sub_msg": "参数非法"
}
```

## 备注
