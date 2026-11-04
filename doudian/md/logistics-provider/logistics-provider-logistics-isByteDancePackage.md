# logistics.isByteDancePackage

> 字节面单信息查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.isByteDancePackage` |
| 中文名 | 字节面单信息查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/isByteDancePackage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/1989 |
| 更新日期 | `2025-04-17` |

## 接口说明

- 文档书: 物流商API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybillCode` | body | string | 是 | 运单号 | `SF123456` |
| `expressCompany` | body | string | 是 | 快递服务商编码（联调时提供枚举） | `shunfeng` |
| `bizType` | body | string | 否 | 业务场景（联调时提供枚举） | `111` |
| `extend` | body | object | 否 | 扩展信息 | `` |
| `  └ queryReason` | body | string | 否 | 查询原因 | `-` |
| `  └ operatorId` | body | string | 否 | 查询人员ID | `-` |
| `  └ postOfficeName` | body | string | 否 | 驿站名 | `-` |
| `  └ postOfficeCode` | body | string | 否 | 驿站编码 | `-` |
| `  └ queryIp` | body | string | 否 | 查询人员实际IP（非集中调用系统网关IP） | `-` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/isByteDancePackage?app_key=your_appkey_here&method=logistics.isByteDancePackage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `isBytedanceWaybill` | string | 是否是字节包裹（1 - 是；2 - 否） | `2` |
| `isBytedanceDec` | string | 是否是字节面单（1 - 是；2 - 否） | `1` |
| `sender` | object | 寄件人信息 | `` |
| `receiver` | object | 收件人信息 | `` |
| `privacyFlag` | string | 是否为隐私面单（1 - 是；2 - 否） | `1` |
| `smsNotSupportedReason` | string | 短信不支持原因 | `收件人手机号格式不正确` |
| `isSmsSupported` | boolean | 是否支持短信代发（true-支持；false-不支持） | `false` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 修改参数 |
| `50002` | 业务处理失败 / 下游接口处理失败（sub_code: isv.business-failed:11004） | 找研发确认 |
| `50002` | 业务处理失败 / 手机号不存在（sub_code: isv.business-failed:11009） | 找测试下个单 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:11003） | 无 |
| `50002` | 业务处理失败 / 未查询到用户信息（sub_code: isv.business-failed:11016） | 无 |
| `50002` | 业务处理失败 / 11021:判断是否抖音面单异常:不支持该物流服务商（sub_code: isv.business-failed:11021） | 11021:判断是否抖音面单异常:不支持该物流服务商 |
| `50002` | 业务处理失败 / 11017:获取授权信息异常（sub_code: isv.business-failed:11017） | 11017:获取授权信息异常 |
| `50002` | 业务处理失败 / 11022:判断是否抖音包裹异常:网络超时（sub_code: isv.business-failed:11022） | 11022:判断是否抖音包裹异常:网络超时 |
| `50002` | 业务处理失败 / 11019:收件人信息获取失败:网络超时（sub_code: isv.business-failed:11019） | 11019:收件人信息获取失败:网络超时 |

## 响应示例

成功：

```json
{
  "data": {
    "isBytedanceDec": "1",
    "isBytedanceWaybill": "2",
    "isSmsSupported": "false",
    "privacyFlag": "1",
    "receiver": {
      "authEndTime": "2022-03-29 09:39:03",
      "authFlag": "1",
      "authStartTime": "2022-03-29 09:39:03",
      "isVirtualNo": "1",
      "mobile": "188****1273",
      "name": "张三",
      "virtualNo": "1863838381-1232",
      "virtualStatus": "1"
    },
    "sender": {
      "authEndTime": "2022-03-29 09:39:03",
      "authFlag": "1",
      "authStartTime": "2022-03-29 09:39:03",
      "isVirtualNo": "1",
      "mobile": "188****1273",
      "name": "张三",
      "virtualNo": "1863838381-1232",
      "virtualStatus": "1"
    },
    "smsNotSupportedReason": "收件人手机号格式不正确"
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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误"
}
```

## 备注
