# 用于卖家和买家沟通后，主动帮买家修改收货信息

> order.addressModify — 用于卖家和买家沟通后，主动帮买家修改收货信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 用于卖家和买家沟通后，主动帮买家修改收货信息 |
| 文档地址 | `/docs/doudian/order/order-order-addressModify` |
| 接口 ID | `doudian.order.order.addressModify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/addressModify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/290 |
| 更新日期 | `2024-07-31` |

## 接口说明

- 文档书: 订单API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单号1 | `4784385386387328490` |
| `post_addr` | body | object | 否 | 修改收货地址，post_addr中的所有字段都必传 | `` |
| `  └ province` | body | object | 否 | 省 | `` |
| `    └ id` | body | string | 否 | 省id | `112` |
| `    └ name` | body | string | 否 | 省名称 | `北京` |
| `  └ city` | body | object | 否 | 城市 | `` |
| `    └ id` | body | string | 否 | 城市id | `110000` |
| `    └ name` | body | string | 否 | 城市名称 | `北京市` |
| `  └ town` | body | object | 否 | 镇 | `` |
| `    └ id` | body | string | 否 | 镇id | `110108` |
| `    └ name` | body | string | 否 | 镇名称 | `海淀区` |
| `  └ street` | body | object | 否 | 街道 | `` |
| `    └ id` | body | string | 否 | 街道id | `110108011` |
| `    └ name` | body | string | 否 | 街道名称 | `中关村街道` |
| `  └ address_detail` | body | string | 否 | 详细地址 | `互联网金融` |
| `  └ land_mark` | body | string | 否 | 暂时未使用的字段 | `空` |
| `post_receiver` | body | string | 否 | 收货人姓名 | `艾一一` |
| `post_tel` | body | string | 否 | 收货人电话号码 | `12312341234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `need_user_review` | boolean | true 表示当前改地址需要消费者确认，消费者确认之后才修改地址 false 表示当前改地址不需要消费者确认，直接修改成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 未更改任何数据，请检查后重新提交（sub_code: isv.parameter-invalid:80004） | 检查参数 |
| `40004` | 非法的参数 / 订单不存在（sub_code: isv.parameter-invalid:20003） | 校验订单之后，再提交 |
| `40004` | 非法的参数 / 手机号格式错误，请修改后重试（sub_code: isv.parameter-invalid:20002） | 校验参数 |
| `50002` | 业务处理失败 / 部分发货不能修改收货地址（sub_code: isv.business-failed:80001） | 不要重试 |
| `50002` | 业务处理失败 / 8888:call ChangeAddress failed（sub_code: isv.business-failed:8888） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 80002:详细地址长度格式不符合要求，请限制在1-60个汉字内（sub_code: isv.business-failed:80002） | 详细地址长度格式不符合要求，请限制在1-60个汉字内 |
| `50002` | 业务处理失败 / 40001:热门商品下单后无法修改地址（sub_code: isv.business-failed:40001） | 热门商品下单后无法修改地址 |
| `50002` | 业务处理失败 / 该订单部分发货，不支持修改地址。（sub_code: isv.business-failed:80102） | - |
| `50002` | 业务处理失败 / 查询订单详情错误（sub_code: isv.business-failed:700007） | - |
| `50002` | 业务处理失败 / 订单不属于当前用户（sub_code: isv.business-failed:50004） | - |
| `50002` | 业务处理失败 / 订单含有跨境商品且用户已支付，不支持修改地址。（sub_code: isv.business-failed:80101） | - |
| `50002` | 业务处理失败 / 收件人长度需为2-25字，请修改（sub_code: isv.business-failed:80120） | - |
| `50002` | 业务处理失败 / 手机号格式有误，请修改（sub_code: isv.business-failed:80119） | - |
| `50002` | 业务处理失败 / 请输入正确的市（sub_code: isv.business-failed:80113） | - |
| `50002` | 业务处理失败 / 新地址与消费者申请修改地址冲突，请和消费者确认后重新提交（sub_code: isv.business-failed:80123） | - |
| `50002` | 业务处理失败 / 请输入正确的区/县（sub_code: isv.business-failed:80114） | - |
| `50002` | 业务处理失败 / 系统识别当前地址为商家地址，请和消费者确认后重新提交（sub_code: isv.business-failed:80118） | - |
| `50002` | 业务处理失败 / 请输入正确的省（sub_code: isv.business-failed:80112） | - |
| `50002` | 业务处理失败 / 新地址是双地址，请修改，避免影响配送（sub_code: isv.business-failed:80117） | - |
| `50002` | 业务处理失败 / 详细地址长度需为2-60字，请修改（sub_code: isv.business-failed:80121） | - |
| `50002` | 业务处理失败 / 请输入正确的街道（sub_code: isv.business-failed:80115） | - |
| `50002` | 业务处理失败 / 当前存在待用户确认的改地址任务（sub_code: isv.business-failed:80131） | - |
| `50002` | 业务处理失败 / 商品已报名平台包邮活动，修改地址不满足活动包邮规则（sub_code: isv.business-failed:80129） | - |
| `50002` | 业务处理失败 / 该订单为小时达订单，不支持修改地址。（sub_code: isv.business-failed:80103） | - |
| `50002` | 业务处理失败 / 当日改地址次数达到限额（sub_code: isv.business-failed:50067） | - |
| `50002` | 业务处理失败 / 数据更新失败（sub_code: isv.business-failed:20015） | - |
| `50002` | 业务处理失败 / 50066:消息幂等校验失败（sub_code: isv.business-failed:50066） | 50066:消息幂等校验失败 |
| `50002` | 业务处理失败 / 20001:service error%!(EXTRA string=消息幂等校验失败)（sub_code: isv.business-failed:20001） | 20001:service error%!(EXTRA string=消息幂等校验失败) |
| `50002` | 业务处理失败 / 80007:订单已享政府补贴,暂不支持修改该地址（sub_code: isv.business-failed:80007） | 80007:订单已享政府补贴,暂不支持修改该地址 |

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
  "sub_code": "isv.parameter-invalid:80004",
  "sub_msg": "未更改任何数据，请检查后重新提交"
}
```

## 备注
