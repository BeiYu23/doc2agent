# 买家地址变更确认

> order.addressConfirm — 买家地址变更确认

| 元信息 | 值 |
| --- | --- |
| 中文名 | 买家地址变更确认 |
| 文档地址 | `/docs/doudian/order/order-order-addressConfirm` |
| 接口 ID | `doudian.order.order.addressConfirm` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/addressConfirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1836 |
| 更新日期 | `2024-06-24` |

## 接口说明

- 文档书: 订单API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 主订单id，注意请求时order/list或 order/detail中返回的主订单id带的‘A’需要截断掉 | `3539925204033339668` |
| `is_approved` | body | mixed | 是 | 0:同意;  拒绝需要传入以下参数：  1001:订单已进入拣货环节  1002:订单已进入配货环节  1003:订单已进入仓库环节 1004:订单已进入出库环节  1005:订单已进入发货环节 300001:省级地址已变更，无法修改地址 300003:市级地址已变更，无法修改地址 300004:区级地址已变更，无法修改地址 300005:联系人已变更，无法修改地址 | `0` |

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
| `50002` | 业务处理失败 / 该任务已经被取消:发起售后自动取消审核任务（sub_code: isv.business-failed:50042） | 请检查订单状态 |
| `50002` | 业务处理失败 / 该任务已经被驳回:订单已进入发货环节（sub_code: isv.business-failed:50041） | 请检查订单状态 |
| `50002` | 业务处理失败 / 该任务已经被通过（sub_code: isv.business-failed:50040） | 该任务已经被通过 |
| `40004` | 非法的参数 / 该订单不存在修改地址审核记录（sub_code: isv.parameter-invalid:50039） | 不存在审核记录，请检查 |
| `40004` | 非法的参数 / 审核开关未打开（sub_code: isv.parameter-invalid:50038） | 审核开关未打开，请检查 |
| `50002` | 业务处理失败 / 审核失败，当前app id无权审核用户的修改地址请求（sub_code: isv.business-failed:50036） | 审核失败，当前app id无权审核用户的修改地址请求 |
| `50002` | 业务处理失败 / 系统异常，请重试（sub_code: isv.business-failed:20003） | 系统异常，请重试 |
| `50002` | 业务处理失败 / 50001:订单号不能为空（sub_code: isv.business-failed:50001） | 50001:订单号不能为空 |

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
  "sub_code": "isv.business-failed:50042",
  "sub_msg": "该任务已经被取消:发起售后自动取消审核任务"
}
```

## 备注
