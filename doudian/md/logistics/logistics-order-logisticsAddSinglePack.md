# order.logisticsAddSinglePack

> 支持同一店铺同一收货人的多个订单发同一个物流包裹

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.order.logisticsAddSinglePack` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/logisticsAddSinglePack` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/563 |
| 更新日期 | `2025-01-22` |

## 接口说明

- 文档书: 物流发货API（版本 V2.12）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id_list` | body | array | 是 | 父订单ID列表 | `["4846347827301748265","4846341672614340433"]` |
| `shipped_order_info` | body | array | 是 | 需要发货的子订单信息 | `` |
| `  └ serial_nos_list` | body | array | 否 | 发货需要回传的SN/69/IMEI码信息 | `` |
| `    └ key` | body | string | 否 | 码的类型 对于空调国补，内机SN对应SN_INDOOR，外机SN对应SN_OUTDOOR | `SN` |
| `    └ value` | body | array | 否 | SN/69/IMEI码的值 | `["123443","51432"]` |
| `  └ shipped_order_id` | body | string | 是 | 需要发货的子订单号 | `4788856825297700215` |
| `  └ shipped_num` | body | number | 是 | 上述子订单的待发货数 | `2` |
| `  └ shipped_item_ids` | body | array | 否 | 已废弃 | `["13123123","442432423"]` |
| `logistics_code` | body | string | 是 | 运单号 | `9595123123` |
| `company` | body | string | 否 | 物流公司名字 | `顺丰` |
| `request_id` | body | string | 是 | 请求唯一标识，相同request_id多次请求，第一次请求成功后，后续的请求会触发幂等，会直接返回第一次请求成功的结果，不会实际触发发货。 | `1267250f-8b9d-4d9e-9fad-0cd9629c83de` |
| `is_reject_refund` | body | boolean | 否 | 是否拒绝退款申请（true表示拒绝退款，并继续发货；不传或为false表示有退款需要处理，拒绝发货），is_refund_reject和is_reject_refund随机使用一个即可 | `true` |
| `logistics_id` | body | string | 否 | 已废弃。物流公司ID。请使用company_code字段。 | `12` |
| `company_code` | body | string | 否 | 物流公司Code，由接口/order/logisticsCompanyLis查询物流公司列表获得，必填 | `shunfeng` |
| `address_id` | body | string | 否 | 发货地址id | `12` |
| `order_serial_number` | body | array | 否 | 订单序列号 | `` |
| `  └ order_id` | body | string | 否 | 父订单号 | `4846347827301748265` |
| `  └ serial_number_list` | body | array | 否 | 商品序列号，单个序列号长度不能超过30位字符，其中手机序列号仅支持填写15～17位数字 | `["546443524543534"]` |
| `store_id` | body | number | 否 | 门店ID | `1234` |
| `after_sale_address_id` | body | number | 否 | 退货地址ID,通过地址库列表【/address/list】接口查询。当传入该字段时，可实现自动审核场景买家退货至商家指定退货地址：例如商家配置的售后小助手以及平台闪电退货规则，会获取发货时传入的after_sale_address_id地址id对应的地址给买家展示进行商品退回； | `12` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pack_id` | string | 包裹id | `7425745832857` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 无默认售后地址，请先设置然后操作发货（sub_code: isv.business-failed:70016） | 请到【抖店左侧导航栏-物流-地址库管理】设置默认售后地址后再操作发货 |
| `20000` | 系统错误 / 发货失败，请稍后重试（sub_code: isp.service-error:70014） | 稍后重试 |
| `50002` | 业务处理失败 / 当前订单存在处理中流程，请稍后重试（sub_code: isv.business-failed:70011） | 稍后重试 |
| `20000` | 系统错误 / 发货失败，请稍后重试（sub_code: isp.service-error:70002） | 稍后重试 |
| `50002` | 业务处理失败 / 该订单已售前退款成功，不能发货（sub_code: isv.business-failed:60068） | 请更新订单信息 |
| `40004` | 非法的参数 / 手机序列号仅支持填写15～17位数字（sub_code: isv.parameter-invalid:60062） | 请输入正确的序列号 |
| `40002` | 缺少必选参数 / 补贴商品发货时需要上传商品序列号（sub_code: isv.missing-parameter:60056） | 补贴商品必须传入序列号，请输入序列号 |
| `50002` | 业务处理失败 / 发货订单中有退款申请需要处理，请先处理（sub_code: isv.business-failed:60040） | 请先处理该订单的售后单，然后再进行发货 |
| `40004` | 非法的参数 / 未查询到此订单（sub_code: isv.parameter-invalid:60033） | 订单号不存在，请检查 |
| `50002` | 业务处理失败 / 该店铺无默认售后地址，请到【抖店左侧导航栏-物流-地址库管理】设置后再操作发货（sub_code: isv.business-failed:60027） | 请到【抖店左侧导航栏-物流-地址库管理】设置默认售后地址后再操作发货 |
| `50002` | 业务处理失败 / 订单已取消，不支持发货（sub_code: isv.business-failed:60021） | 请更新订单信息 |
| `40004` | 非法的参数 / 暂不支持该物流公司或物流商已失效（sub_code: isv.parameter-invalid:60018） | company_code参数错误。请通过/order/logisticsCompanyList接口获取company_code |
| `40004` | 非法的参数 / 物流单号不符合规则（sub_code: isv.parameter-invalid:60017） | company_code和logistics_code不匹配，请检查物流公司和单号是否正确 |
| `40002` | 缺少必选参数 / 物流公司Code不能为空（sub_code: isv.missing-parameter:60011） | company_code参数错误。请通过/order/logisticsCompanyList接口获取company_code |
| `40002` | 缺少必选参数 / 订单号不能为空（sub_code: isv.missing-parameter:50049） | 请输入正确的订单号 |
| `40004` | 非法的参数 / 订单号为空或格式错误（sub_code: isv.parameter-invalid:50001） | 请输入正确的订单号 |
| `40002` | 缺少必选参数 / 物流公司编码(company_code)字段不能为空。注：物流公司ID(logisitcs_id)字段已废弃（sub_code: isv.missing-parameter:60083） | 请通过/order/logisticsCompanyList接口获取company_code |
| `50002` | 业务处理失败 / 60072:该店铺无默认发货地址，请到【抖店左侧导航栏-物流-地址库管理】设置后再操作发货（sub_code: isv.business-failed:60072） | 该店铺无默认发货地址，请到【抖店左侧导航栏-物流-地址库管理】设置后再操作发货 |
| `50002` | 业务处理失败 / 60046:序列号长度不能超过30位字符（sub_code: isv.business-failed:60046） | 若传入了序列号，则序列号长度需要在1-30位字符之间，请检查后重新发货 |
| `50002` | 业务处理失败 / 60069:该订单为质检订单，请在商家后台送检页面进行送检发货操作（sub_code: isv.business-failed:60069） | 该订单为质检订单，请在商家后台送检页面进行送检发货操作 |
| `50002` | 业务处理失败 / 当前发货地址存在异常，请前往抖店PC端「物流-地址库管理」修改后重试（sub_code: isv.business-failed:60070） | 当前发货地址存在异常，请前往抖店PC端「物流-地址库管理」修改后重试 |
| `50002` | 业务处理失败 / 该订单补贴商品的序列号已经上传，请重新填写（sub_code: isv.business-failed:60047） | 该订单补贴商品的序列号已经上传，请重新填写 |
| `50002` | 业务处理失败 / 发货失败，请稍后重试（sub_code: isv.business-failed:70009） | 请稍后重试 |
| `50002` | 业务处理失败 / 该订单不支持使用其它物流进行发货（sub_code: isv.business-failed:60026） | 请检查订单和物流信息 |
| `50002` | 业务处理失败 / 70023:没有能发货的订单，请修改后重试（sub_code: isv.business-failed:70023） | 没有能发货的订单，请修改后重试 |
| `50002` | 业务处理失败 / 70020:运单号收件人电话及地址与该订单收件人电话及地址均不一致，请核实后更新快递单号（sub_code: isv.business-failed:70020） | 运单号收件人电话及地址与该订单收件人电话及地址均不一致，请核实后更新快递单号 |
| `50002` | 业务处理失败 / 60016:商品单单号为空或者格式错误（sub_code: isv.business-failed:60016） | 商品单单号为空或者格式错误 |
| `50002` | 业务处理失败 / 60127:发货信息填写有误，请检查物流单号、物流公司是否填写/选择正确（sub_code: isv.business-failed:60127） | 发货信息填写有误，请检查物流单号、物流公司是否填写/选择正确 |
| `50002` | 业务处理失败 / 60110:订单已发货，不允许再次执行发货（sub_code: isv.business-failed:60110） | 订单已发货，不允许再次执行发货 |
| `50002` | 业务处理失败 / 60113:订单已完结，禁止发货（sub_code: isv.business-failed:60113） | 订单已完结，禁止发货 |
| `50002` | 业务处理失败 / 60124:系统连接错误，请稍后再试（sub_code: isv.business-failed:60124） | 系统连接错误，请稍后再试 |
| `50002` | 业务处理失败 / 8888:系统繁忙，请稍后重试（sub_code: isv.business-failed:8888） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 60109:订单正在风控审核中，风控审核时效1~2小时，请等待订单变为“备货中”状态后重试（sub_code: isv.business-failed:60109） | 订单正在风控审核中，风控审核时效1~2小时，请等待订单变为“备货中”状态后重试 |
| `50002` | 业务处理失败 / 60123:当前订单为供应链订单，需: 海口珍珠恋服饰设计有限公司 帮助发货（sub_code: isv.business-failed:60123） | 当前订单为供应链订单，需: 海口珍珠恋服饰设计有限公司 帮助发货 |
| `50002` | 业务处理失败 / 60138:订单需送货上门，请使用支持送货上门的物流公司发货（sub_code: isv.business-failed:60138） | 订单需送货上门，请使用支持送货上门的物流公司发货 |
| `50002` | 业务处理失败 / 70021:多个订单的收货人手机号/收货地址不一致，请核对发货数据（sub_code: isv.business-failed:70021） | 多个订单的收货人手机号/收货地址不一致，请核对发货数据 |
| `50002` | 业务处理失败 / 60101:非本店铺订单，操作失败（sub_code: isv.business-failed:60101） | 非本店铺订单，操作失败 |
| `50002` | 业务处理失败 / 请传入退货地址，提高退换货的履约准确率（sub_code: isv.business-failed:700029） | 请传入退货地址，提高退换货的履约准确率 |
| `50002` | 业务处理失败 / 70019:物流单号首条轨迹产生时间早于订单支付时间，请核实后更新单号（sub_code: isv.business-failed:70019） | 请检查单号时间 |
| `50002` | 业务处理失败 / 70018:物流单号已被快递回收或取消，无法继续使用，请核实后更新单号（sub_code: isv.business-failed:70018） | 请检查单号状态 |
| `50002` | 业务处理失败 / 60116:订单中商品由平台仓发货，无需手动发货（sub_code: isv.business-failed:60116） | 该订单无需手动发货 |
| `50002` | 业务处理失败 / 60118:订单售后信息异常，请稍后重试（sub_code: isv.business-failed:60118） | 请重试 |
| `50002` | 业务处理失败 / 70022:物流单号已被其他订单使用，且收货人手机号/收货地址不一致，请核实后更新单号（sub_code: isv.business-failed:70022） | 请跟换物流单号 |
| `50002` | 业务处理失败 / 700006:小时达订单不支持拆单发货（sub_code: isv.business-failed:700006） | 不支持拆单发货 |
| `50002` | 业务处理失败 / 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值（sub_code: isv.business-failed:120064） | 120064:该订单为偏远地区中转订单，您的账户余额不够支付中转运费，不能进行中转，请前往管家账户充值 |
| `50002` | 业务处理失败 / 60143:周期购订单非最新一期sku单不允许发货（sub_code: isv.business-failed:60143） | 60143:周期购订单非最新一期sku单不允许发货 |
| `50002` | 业务处理失败 / 该订单为收礼订单，不支持发货，请对对应送礼单操作（sub_code: isv.business-failed:700088） | 该订单为收礼订单，不支持发货，请对对应送礼单操作 |

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
  "sub_code": "isv.business-failed:70016",
  "sub_msg": "无默认售后地址，请先设置然后操作发货"
}
```

## 备注
