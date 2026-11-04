# 此接口用来帮助商家进行延时收货

> afterSale.timeExtend — 此接口用来帮助商家进行延时收货，商家可以在还有2天到期的时间进行操作，会在原有剩余时间的基础上增加7天。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 此接口用来帮助商家进行延时收货 |
| 文档地址 | `/docs/doudian/refund/refund-afterSale-timeExtend` |
| 接口 ID | `doudian.refund.afterSale.timeExtend` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/timeExtend` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/770 |
| 更新日期 | `2021-08-03` |

## 接口说明

- 文档书: 售后退款API（版本 V3.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 售后单号 | `7036706918206930000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/timeExtend?app_key=your_appkey_here&method=afterSale.timeExtend&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 用户发货五天后才能延长收货（sub_code: isv.parameter-invalid:10001） | 检查入参 |
| `50002` | 业务处理失败 / 10014:查找售后单对应的用户信息失败（sub_code: isv.business-failed:10014） | 检查入参 |

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
  "sub_code": "isv.parameter-invalid:10001",
  "sub_msg": "用户发货五天后才能延长收货"
}
```

## 备注
