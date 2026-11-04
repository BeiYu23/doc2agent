# supplyChain.returnOrder.operate

> 供应商操作售后单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.returnOrder.operate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/returnOrder/operate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/4035 |
| 更新日期 | `2023-06-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `return_order_no` | body | string | 是 | 售后单号 | `"GSH123123123123"` |
| `operate_type` | body | string | 是 | 操作类型，目前支持 同意退款：CONFIRM_REFUNDD 确认收货：CONFIRM_RETURNED 拒绝售后：REJECT | `"CONFIRM_RETURNED"` |
| `refuse_reason` | body | string | 否 | 售后拒绝原因 | `"售后拒绝原因"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 请求响应码 | `0` |
| `msg` | string | 响应信息 | `"success"` |
| `success` | boolean | 操作是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数解析异常（sub_code: isv.parameter-invalid:1020） | 重新填写入参 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000） | 重试 |
| `20000` | 系统错误 / 业务处理失败（sub_code: isp.service-error:1040） | 根据提示处理 |
| `50002` | 业务处理失败 / 2012:当前售后单状态不允许该操作（sub_code: isv.business-failed:2012） | 2012:当前售后单状态不允许该操作 |
| `50002` | 业务处理失败 / 2033:订单未处于进行中，无法拒绝售后（sub_code: isv.business-failed:2033） | 2033:订单未处于进行中，无法拒绝售后 |

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
  "sub_code": "isv.parameter-invalid:1020",
  "sub_msg": "参数解析异常"
}
```

## 备注
