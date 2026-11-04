# 订单发货后

> order.addSerialNumber — 订单发货后，如需修改商品序列号或补充上传商品序列号，可调用此接口进行修改或上传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 订单发货后 |
| 文档地址 | `/docs/doudian/order/order-order-addSerialNumber` |
| 接口 ID | `doudian.order.order.addSerialNumber` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/addSerialNumber` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1289 |
| 更新日期 | `2021-09-27` |

## 接口说明

- 文档书: 订单API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单号 | `4819248074018981281` |
| `serial_number_list` | body | array | 是 | 商品序列号，序列号长度不能超过30位字符，其中手机序列号仅支持填写15～17位数字；最多支持传入20个序列号 | `["546443524543534","646443524543534"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/addSerialNumber?app_key=your_appkey_here&method=order.addSerialNumber&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 该订单状态不支持序列号上传（sub_code: isv.business-failed:60049） | 停止操作 |
| `50002` | 业务处理失败 / 补贴商品发货时需要上传商品序列号（sub_code: isv.business-failed:60056） | 输入正确的序列号 |
| `20000` | 系统错误 / 查询订单信息异常（sub_code: isp.service-error:50024） | 重试 |
| `40002` | 缺少必选参数 / 订单号不能为空（sub_code: isv.missing-parameter:50049） | 传入需上传序列号的订单号 |
| `40002` | 缺少必选参数 / 序列号不能为空（sub_code: isv.missing-parameter:60048） | 传入需上传的序列号 |
| `40004` | 非法的参数 / 序列号长度不能超过30位字符（sub_code: isv.parameter-invalid:60046） | 输入正确的序列号 |
| `20000` | 系统错误 / 系统异常，请重试（sub_code: isp.service-error:20003） | 重试 |
| `50002` | 业务处理失败 / IMEI号仅支持填写15～17位数字（sub_code: isv.business-failed:60062） | 输入正确的序列号 |
| `50002` | 业务处理失败 / 该订单补贴商品的序列号已经上传，请重新填写（sub_code: isv.business-failed:60047） | 重新输入正确的序列号 |

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
  "sub_code": "isv.business-failed:60049",
  "sub_msg": "该订单状态不支持序列号上传"
}
```

## 备注
