# 更新整单发货物流信息

> order.logisticsEdit — 更新整单发货物流信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新整单发货物流信息 |
| 文档地址 | `/docs/doudian/logistics/logistics-order-logisticsEdit` |
| 接口 ID | `doudian.logistics.order.logisticsEdit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/logisticsEdit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/390 |
| 更新日期 | `2026-09-03` |

## 接口说明

- 文档书: 物流发货API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单ID | `4782813149182887526A` |
| `logistics_id` | body | mixed | 否 | 已废弃。物流公司ID。请使用company_code字段。 | `12` |
| `company_code` | body | string | 否 | 物流公司code,由接口/order/logisticsCompanyList返回的物流公司列表获得，必填 | `shunfeng、qita` |
| `logistics_code` | body | string | 否 | 快递单号 | `sf1231231231234` |
| `company` | body | string | 否 | 已废弃。物流公司名称 | `顺丰` |
| `store_id` | body | mixed | 否 | 门店ID，抖超业务使用 | `1234` |
| `after_sale_address_id` | body | mixed | 否 | 退货地址ID,通过地址库列表【/address/list】接口查询。当传入该字段时，可实现自动审核场景买家退货至商家指定退货地址：例如商家配置的售后小助手以及平台闪电退货规则，会获取发货时传入的after_sale_address_id地址id对应的地址给买家展示进行商品退回； | `1` |
| `product_orders` | body | array | 否 | 挂在商品单上的信息，只是用于传递和商品单关联的信息，比如SN/69/IMEI码。比如，店铺单下有A、B、C三个商品单，其中A单需要SN/69/IMEI码，这时候只需要把A单关联的SN/69/IMEI传递过来即可。 | `` |
| `  └ serial_no_list` | body | array | 否 | 需要的SN/69/IMEI码列表。 | `` |
| `    └ value` | body | array | 否 | SN/69/IMEI码的值。 | `["12343","abcd"]` |
| `    └ key` | body | string | 否 | SN/69/IMEI码的类型 | `SN` |
| `  └ product_order_id` | body | string | 否 | 商品单单号 | `4782813149182887526` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/logisticsEdit?app_key=your_appkey_here&method=order.logisticsEdit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 此订单状态不允许重新发货（sub_code: isv.business-failed:10007） | 请重新获取订单信息 |
| `40004` | 非法的参数 / 运单号不符合规则，请核对单号大小写、单号位数、快递公司是否正确（sub_code: isv.parameter-invalid:10002） | 请检查物流公司与物流单号是否匹配 |
| `20000` | 系统错误 / 重新发货失败，请稍后重试（sub_code: isp.service-error:10001） | 请稍后重试 |
| `50002` | 业务处理失败 / 60024:该订单不可自行操作重新发货，请联系跨境服务商进行操作（sub_code: isv.business-failed:60024） | 联系跨境服务商进行处理 |
| `50002` | 业务处理失败 / 物流单号错误。原因：发货信息填写有误，请检查物流单号、物流公司是否填写/选择正确（sub_code: isv.business-failed:60017） | 请检查物流公司与物流单号是否匹配 |
| `50002` | 业务处理失败 / 物流公司错误。原因：暂不支持该物流商，请检查物流商编码后重新发货（sub_code: isv.business-failed:60018） | 请检查物流公司与物流单号是否匹配 |
| `50002` | 业务处理失败 / 该订单的订单状态不允许重新发货（sub_code: isv.business-failed:60021） | 请检查订单状态是否允许发货 |
| `40004` | 非法的参数 / 物流公司编码(company_code)字段不能为空。注：物流公司ID(logisitcs_id)字段已废弃（sub_code: isv.parameter-invalid:60083） | 请检查物流公司与物流单号是否匹配 |
| `50002` | 业务处理失败 / 物流单号校验失败，请稍后重试（sub_code: isv.business-failed:70013） | 请检查物流公司与物流单号是否匹配 |
| `40004` | 非法的参数 / 物流单号不能为空（sub_code: isv.parameter-invalid:60014） | 请检查物流公司与物流单号是否匹配 |
| `50002` | 业务处理失败 / 该订单为质检订单，请在商家后台送检页面进行送检发货操作（sub_code: isv.business-failed:60023） | 请在商家后台送检页面进行送检发货 |
| `20000` | 系统错误 / 重新发货失败，请稍后重试（sub_code: isp.service-error:70008） | 请稍后重试 |
| `50002` | 业务处理失败 / 该订单不支持使用其它物流进行发货（sub_code: isv.business-failed:60026） | 不支持使用其他物流发货 |
| `50002` | 业务处理失败 / 退货地址在地址库不存在，请刷新重试（sub_code: isv.business-failed:60134） | 该发货地址在商家地址库不存在，商家重新选择可用的发货地址或者前往抖店PC端「订单-发货管理-物流工具-地址库管理」设置后重试 |
| `50002` | 业务处理失败 / 70011:包裹单号缺失，请修改后重试（sub_code: isv.business-failed:70011） | 仅支持整单接口发货的物流修改，如订单是一单多包或合单发货的订单，请使用【/order/logisticsEditByPack】接口更新； |
| `50002` | 业务处理失败 / 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值（sub_code: isv.business-failed:120064） | 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值 |
| `50002` | 业务处理失败 / 700003:store_id为空/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:700003） | 700003:store_id为空/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 60132:系统异常，请稍后重试（sub_code: isv.business-failed:60132） | 60132:系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 700005:小时购订单不支持该快递公司发货（sub_code: isv.business-failed:700005） | 700005:小时购订单不支持该快递公司发货 |
| `50002` | 业务处理失败 / 700002:发货订单包含非本门店订单，请重试（sub_code: isv.business-failed:700002） | 700002:发货订单包含非本门店订单，请重试 |
| `50002` | 业务处理失败 / 您选择的订单中包含偏远中转订单，因货款及抖店钱包余额不足无法支付中转运费(每笔2.5元)发货失败，可在抖店PC端充值后重试，路径：账户中心 > 其他账户 > 抖店钱包（sub_code: isv.business-failed:120066） | 您选择的订单中包含偏远中转订单，因货款及抖店钱包余额不足无法支付中转运费(每笔2.5元)发货失败，可在抖店PC端充值后重试，路径：账户中心 > 其他账户 > 抖店钱包 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:120035） | 系统繁忙，请稍后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10007",
  "sub_msg": "此订单状态不允许重新发货"
}
```

## 备注
