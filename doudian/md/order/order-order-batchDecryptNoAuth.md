# order.batchDecryptNoAuth

> 1、接口支持解密在文档字段有“密文”红色标识字段值：收件人电话收件人姓名；详细地址；账号值；证件号；证件姓名 2、不支持解密doudian_open_id字段加密用户ID串 3、最大支持一次解密50条数据 4、cipher_infos字段待解密的密文列表示

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.batchDecryptNoAuth` |
| 中文名 | 接口支持解密在文档字段有“密文”红色标识字段值… |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/batchDecryptNoAuth` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/4685 |
| 更新日期 | `2023-09-11` |

## 接口说明

- 文档书: 订单API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cipher_infos` | body | array | 是 | 待解密值集合，最大支持一次解密50条。待解密的密文列表示例，入参结构{"cipher_infos":[{"order_id”:”订单号”,”cipher_text”:”待解密值”},{“ order_id”:”订单号”,”cipher_text”:”待解密值”}]} | `` |
| `  └ order_id` | body | string | 是 | 订单号 | `4933609365066313446` |
| `  └ cipher_text` | body | string | 是 | 待解密值 | `$c0qBj0QrZm9qae50eoBTInPj8PWvCjUyafxWt5cELI0=$YOUR_SECRET_KEY*YOUR_SECRET_KEY$1$$,#ML3B#YOUR_SECRET_KEY*YOUR_SECRET_KEY#1##` |
| `account_id` | body | string | 否 | 服务商账号体系中，商户的账户ID，每个ISV下需要保证唯一，可选格式:独立生成的账户唯一标识 | `dy1001` |
| `account_type` | body | string | 否 | 商户的账户ID类型；服务商账号中的主-main_account；子账号-sub_account； | `main_account` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `decrypt_infos` | array | 解密列表 | `` |
| `custom_err` | object | 业务错误 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务处理失败,详情请看sub_msg（sub_code: isv.business-failed:300003） | 业务处理失败,详情请看sub_msg |
| `50002` | 业务处理失败 / 300008:解密接口存在部分失败（sub_code: isv.business-failed:300008） | 无 |
| `50002` | 业务处理失败 / 300001:解密错误: 批量解密存在部分失败（sub_code: isv.business-failed:300001） | 无 |

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
  "sub_code": "isv.business-failed:300003",
  "sub_msg": "业务处理失败,详情请看sub_msg"
}
```

## 备注
