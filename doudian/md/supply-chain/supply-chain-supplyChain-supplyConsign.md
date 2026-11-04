# supplyChain.supplyConsign

> 供货单发货

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyConsign` |
| 中文名 | 供货单发货 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/supplyConsign` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/1733 |
| 更新日期 | `2025-04-29` |

## 接口说明

- 文档书: 供销平台API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_no` | body | string | 是 | 供货单号 | `CT7069898293592` |
| `tms_code` | body | string | 是 | 快递商编码，使用package_list进行多包裹发货时，该字段传"" | `shunfeng` |
| `tracking_no` | body | string | 是 | 快递单号,使用package_list进行多包裹发货时，该字段传"" | `SF53798222352` |
| `sender_addr` | body | object | 否 | 发货人地址结构 | `` |
| `  └ province_name` | body | string | 是 | 省名称 | `浙江省` |
| `  └ city_name` | body | string | 是 | 市名称 | `杭州市` |
| `  └ district_name` | body | string | 是 | 区名称 | `余杭区` |
| `  └ street_name` | body | string | 否 | 街道名称，没有则填空字符 | `仓前街道` |
| `  └ addr_detail` | body | string | 是 | 剩余详细地址 | `文一西路1号` |
| `sender_name` | body | string | 否 | 发货人姓名 | `张三` |
| `sender_tel` | body | string | 否 | 发货人联系电话 | `13252354532` |
| `package_list` | body | array | 否 | 包裹列表，用于拆包发货 | `` |
| `  └ sn` | body | string | 否 | 电器sn码 | `1234123` |
| `  └ imei` | body | string | 否 | 手机类imei码 | `12345` |
| `  └ tms_code` | body | string | 是 | 快递商编码 | `shunfeng` |
| `  └ ship_cnt` | body | mixed | 是 | 发货数量 | `1` |
| `  └ track_no` | body | string | 是 | 快递单号 | `SF53798222352` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyConsign?app_key=your_appkey_here&method=supplyChain.supplyConsign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | true=发货成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2000） | 请参考错误信息，或联系对接人员 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:1000） | 请稍后再试，或联系对接人员 |
| `40004` | 非法的参数 / 非法参数请求（sub_code: isv.parameter-invalid:1020） | 请参考错误信息，或联系对接人员 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "业务处理失败"
}
```

## 备注
