# 更新订单的物流面单信息

> btas.updateOrderCourier — 更新订单的物流面单信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新订单的物流面单信息 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-updateOrderCourier` |
| 接口 ID | `doudian.btas-inspect.btas.updateOrderCourier` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/updateOrderCourier` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/3528 |
| 更新日期 | `2023-04-12` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `0454123123` |
| `courier_code` | body | string | 是 | 快递单号(可以通过电子面单获取） | `SF0234231213232423` |
| `logistics_name_en` | body | string | 是 | 快递公司名称 | `shunfeng` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/updateOrderCourier?app_key=your_appkey_here&method=btas.updateOrderCourier&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -1:当前账号不能访问该接口，请联系开发人员配置（sub_code: isv.business-failed:-1） | 联系开发者 |

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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "-1:当前账号不能访问该接口，请联系开发人员配置"
}
```

## 备注
