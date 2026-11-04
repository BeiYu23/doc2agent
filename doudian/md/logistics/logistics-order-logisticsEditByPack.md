# order.logisticsEditByPack

> 调用场景：
1、支持修改一单多包（拆单发货）【/order/logisticsAddMultiPack】和合单发货【/order/logisticsAddSinglePack】接口，发货成功的订单；
2、注意：整单发货修改物流请使用【/order/logi

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.order.logisticsEditByPack` |
| 中文名 | 调用场景 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/logisticsEditByPack` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/539 |
| 更新日期 | `2022-12-05` |

## 接口说明

- 文档书: 物流发货API（版本 V3.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 父订单ID，可使用【/order/searchList】接口获取； | `6496679971677798670` |
| `pack_id` | body | string | 是 | 包裹ID；可使用【/order/orderDetail 】和【/order/searchList】在响应参数中获取delivery_id字段； | `23123123` |
| `logistics_code` | body | string | 是 | 运单号 | `9595123123` |
| `company_code` | body | string | 否 | 物流公司ID，由接口【/order/logisticsCompanyList】返回的物流公司列表获得，必填 | `shunfeng` |
| `logistics_id` | body | string | 否 | 已废弃。物流公司ID。请使用company_code字段。 | `12` |
| `store_id` | body | number | 否 | 门店ID，抖超业务使用 | `1234` |
| `after_sale_address_id` | body | number | 否 | 退货地址ID,通过地址库列表【/address/list】接口查询。当传入该字段时，可实现自动审核场景买家退货至商家指定退货地址：例如商家配置的售后小助手以及平台闪电退货规则，会获取发货时传入的after_sale_address_id地址id对应的地址给买家展示进行商品退回； | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 请求校验物流公司及物流单号失败，请稍后重试（sub_code: isp.service-error:70013） | 稍后重试 |
| `20000` | 系统错误 / 发货失败，请稍后重试（sub_code: isp.service-error:70011） | 请参考接口错误信息，修复后重试 |
| `20000` | 系统错误 / 发货失败，请稍后重试（sub_code: isp.service-error:70008） | 稍后重试 |
| `50002` | 业务处理失败 / 该订单的订单状态不允许发货（sub_code: isv.business-failed:60021） | 请重新获取订单信息 |
| `40004` | 非法的参数 / 物流单号不符合规则（sub_code: isv.parameter-invalid:60017） | 物流单号不符合规则或不匹配 |
| `40002` | 缺少必选参数 / 物流公司编码(company_code)字段不能为空。注：物流公司ID(logisitcs_id)字段已废弃（sub_code: isv.missing-parameter:60083） | 请通过/order/logisticsCompanyList接口获取company_code |
| `50002` | 业务处理失败 / 60011:物流公司Code不能全为空（sub_code: isv.business-failed:60011） | 请通过/order/logisticsCompanyList接口获取company_code |
| `50002` | 业务处理失败 / 暂不支持该物流商，请检查物流商编码后重新发货（sub_code: isv.business-failed:60018） | 请通过/order/logisticsCompanyList接口获取company_code |
| `50002` | 业务处理失败 / 发货失败，请稍后重试（sub_code: isv.business-failed:8888） | 稍后重试 |
| `50002` | 业务处理失败 / 订单不支持使用其它物流进行发货（sub_code: isv.business-failed:60026） | 订单不支持使用其它物流进行发货 |
| `50002` | 业务处理失败 / 退货地址在地址库不存在，请刷新重试（sub_code: isv.business-failed:60134） | 该发货地址在商家地址库不存在，商家重新选择可用的发货地址或者前往抖店PC端「订单-发货管理-物流工具-地址库管理」设置后重试 |
| `50002` | 业务处理失败 / 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值（sub_code: isv.business-failed:120064） | 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值 |
| `50002` | 业务处理失败 / 60023:该订单为质检订单，请在商家后台送检页面进行重新发货操作（sub_code: isv.business-failed:60023） | 60023:该订单为质检订单，请在商家后台送检页面进行重新发货操作 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:70013",
  "sub_msg": "请求校验物流公司及物流单号失败，请稍后重试"
}
```

## 备注
