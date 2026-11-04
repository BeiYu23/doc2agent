# instantShopping.starhub.querySaleOutboundOrderReceiver

> 服务商主动向抖音获取城市仓单收货信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.instantShopping.starhub.querySaleOutboundOrderReceiver` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6914 |
| 更新日期 | `2024-11-21` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outbound_order_id` | body | string | 否 | 抖音出库主单号 | `124124` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 收货人信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 仓单id未找到（sub_code: isv.parameter-invalid:40001） | 检查仓单id是否异常 |
| `50002` | 业务处理失败 / 50040:获取虚拟号失败（sub_code: isv.business-failed:50040） | 获取虚拟号失败，请重试 |
| `50002` | 业务处理失败 / 1004:Internal Server Error（sub_code: isv.business-failed:1004） | 1004:Internal Server Error |
| `50002` | 业务处理失败 / 40006:仓单已完结,不可查询收货人信息（sub_code: isv.business-failed:40006） | 40006:仓单已完结,不可查询收货人信息 |

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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "仓单id未找到"
}
```

## 备注
