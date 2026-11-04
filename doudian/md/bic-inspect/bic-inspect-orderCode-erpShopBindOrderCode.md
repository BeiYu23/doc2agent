# orderCode.erpShopBindOrderCode

> 质检/查验订单商家发货接口，调用后会绑定订单和订单码，并生成qic入库单，
delivery_type 是 【0】&& ship_type 是【1】，对应一单一包裹模式；
delivery_type 是 【0】&& ship_type 是【3】，对应混订单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bic-inspect.orderCode.erpShopBindOrderCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/erpShopBindOrderCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/51/806 |
| 更新日期 | `2024-08-01` |

## 接口说明

- 文档书: BIC质检API（版本 V1.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_package_id` | body | string | 是 | 商家包裹id | `6941730766905180453` |
| `delivery_type` | body | number | 是 | 送检方式 | `0` |
| `ship_type` | body | number | 是 | 出仓方式 | `1` |
| `order_list` | body | array | 是 | 订单列表 | `` |
| `  └ agency_id` | body | number | 否 | 质检机构ID，复检订单必填，需要与仓库编码对应上 | `101` |
| `  └ warehouse_code` | body | string | 否 | 仓库编码，复检订单必填 | `02` |
| `  └ is_reinspection` | body | string | 否 | 1：是，2：否。注意：不是复检订单不可传0，直接不入参is_reinspection即可 | `1` |
| `  └ order_id` | body | number | 是 | 订单id | `4782860977949521619` |
| `  └ order_code` | body | string | 是 | 订单码 | `0822597409` |
| `  └ logistics_code` | body | string | 否 | 运单号 | `9595123123` |
| `  └ logistics_id` | body | number | 否 | 物流公司id | `12` |
| `  └ order_detail` | body | array | 否 | 商品详情 | `` |
| `    └ combo_id` | body | number | 是 | 该订单购买的商品对应平台的 sku_id | `1696289587496995` |
| `    └ shop_qty` | body | number | 是 | 发货数量 | `1` |
| `    └ sku_barcode` | body | string | 否 | 商品条码 | `预留扩展字段` |
| `    └ unique_code` | body | string | 否 | "商品唯一标识编码  （如：海宁基地服饰的溯源码信息）" | `预留扩展字段` |
| `    └ lot01` | body | string | 否 | 批次属性01 | `预留扩展字段` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_list` | array | 订单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 传入订单码有误（sub_code: isv.parameter-invalid:6011） | 订单码不存在，确认输入的订单码是否有误 |
| `40004` | 非法的参数 / 质检机构有误（sub_code: isv.parameter-invalid:-1） | 请检查发货策略是否配置，稍后重试 |
| `50002` | 业务处理失败 / 该订单不是待绑码状态，不允许绑码（sub_code: isv.business-failed:6071） | 该订单不需要操作绑码 |
| `50002` | 业务处理失败 / 订单处理中，请稍后再试（sub_code: isv.business-failed:1001） | 请稍后重试 |
| `40004` | 非法的参数 / 商家发货包裹已经存在，不支持重发（sub_code: isv.parameter-invalid:1000） | 商家发货包裹已经存在，不支持重发 |
| `20000` | 系统错误 / 调用下游超时（sub_code: isp.service-error:6014） | 接口超时，请重试 |
| `50002` | 业务处理失败 / 6012:该订单码已绑定，不可再被绑定（sub_code: isv.business-failed:6012） | 请检查订单码是否正确，更换订单码 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:6038） | 请检查订单是否正确，确认无误稍后重试 |
| `40004` | 非法的参数 / 非法操作（sub_code: isv.parameter-invalid:6041） | 订单不属于当前店铺 |
| `40004` | 非法的参数 / 入参为空（sub_code: isv.parameter-invalid:20001） | 入参不能为空，填入合法参数 |
| `50002` | 业务处理失败 / 仓库和机构关系错误（sub_code: isv.business-failed:20020） | 检查仓库和机构的对应关系 |
| `50002` | 业务处理失败 / 复检订单额度不足（sub_code: isv.business-failed:20021） | 选择非复检绑码 |
| `50002` | 业务处理失败 / 当前机构产能不足（sub_code: isv.business-failed:20022） | 更换质检机构 |
| `50002` | 业务处理失败 / 材质无法检测（sub_code: isv.business-failed:20023） | 更换质检机构 |
| `50002` | 业务处理失败 / 1002:系统错误，请稍后重试（sub_code: isv.business-failed:1002） | 1002:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 1006:选择的【不二】睡美人蓝松DIY随形耳钩，不能与其他订单一起绑码（sub_code: isv.business-failed:1006） | 1006:选择的【不二】睡美人蓝松DIY随形耳钩，不能与其他订单一起绑码 |
| `50002` | 业务处理失败 / 1004:调用入库单接口失败（sub_code: isv.business-failed:1004） | 1004:调用入库单接口失败 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:6011",
  "sub_msg": "传入订单码有误"
}
```

## 备注
