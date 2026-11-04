# 质检机构_根据自提码确认商家自提完成

> btas.sc.confirmOrderByPickupCode — 质检机构_根据自提码确认商家自提完成

| 元信息 | 值 |
| --- | --- |
| 中文名 | 质检机构_根据自提码确认商家自提完成 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-sc-confirmOrderByPickupCode` |
| 接口 ID | `doudian.btas-inspect.btas.sc.confirmOrderByPickupCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/confirmOrderByPickupCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2941 |
| 更新日期 | `2023-02-09` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code_list` | body | array | 是 | 订单码码列表 | `["233211"]` |
| `pickup_code` | body | string | 是 | 自提码 | `232234` |
| `sc_id` | body | number | 是 | 质检机构ID | `3` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/sc/confirmOrderByPickupCode?app_key=your_appkey_here&method=btas.sc.confirmOrderByPickupCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
