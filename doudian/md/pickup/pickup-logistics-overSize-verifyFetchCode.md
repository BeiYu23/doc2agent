# logistics.overSize.verifyFetchCode

> 大件取件码核销

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.pickup.logistics.overSize.verifyFetchCode` |
| 中文名 | 大件取件码核销 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1526/6709 |
| 更新日期 | `2024-07-19` |

## 接口说明

- 文档书: 上门取件API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 商家订单号 | `4732078173688851864` |
| `waybill_code` | body | string | 否 | 运单号 | `JT0101001010` |
| `verify_code` | body | string | 否 | 取件码 | `6472` |
| `operate_time` | body | string | 否 | 核销操作时间 | `2021-01-19 15:12:23` |
| `express` | body | string | 否 | 承运商 | `服务商` |

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
| `50002` | 业务处理失败 / 11410:取件码错误（sub_code: isv.business-failed:11410） | 11410:取件码错误 |
| `50002` | 业务处理失败 / 11413:取消后不支持核销（sub_code: isv.business-failed:11413） | 11413:取消后不支持核销 |
| `50002` | 业务处理失败 / 10002:当前状态不允许核销取件码（sub_code: isv.business-failed:10002） | 10002:当前状态不允许核销取件码 |

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
  "sub_code": "isv.business-failed:11410",
  "sub_msg": "11410:取件码错误"
}
```

## 备注
