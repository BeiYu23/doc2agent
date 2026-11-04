# 质检机构获取该机构的订单状态信息

> btas.sc.getInspectionOrder — 质检机构获取该机构的订单状态信息，包含履约状态，取消状态，送检状态和发货状态等。
注意该字段需要手动配置接口权限，且仅能查询当前机构的订单。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 质检机构获取该机构的订单状态信息 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-sc-getInspectionOrder` |
| 接口 ID | `doudian.btas-inspect.btas.sc.getInspectionOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/getInspectionOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/3529 |
| 更新日期 | `2023-04-25` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 店铺单ID | `463123124535345` |
| `order_code` | body | string | 否 | 订单码，与订单ID二选一填入 | `0431231253` |
| `sc_id` | body | number | 否 | 质检机构ID，不能为空 | `58` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/pushOutboundFeedback?app_key=your_appkey_here&method=yunc.pushOutboundFeedback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_orders` | array | 订单列表 | `` |
| `order_id` | string | 订单ID | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 订单不存在（sub_code: isp.service-error:4000） | 重试 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:2030） | 检查订单ID和订单码是否传 |
| `50002` | 业务处理失败 / 非法访问，没有获取到授权店铺信息（sub_code: isv.business-failed:-1） | - |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:4000",
  "sub_msg": "订单不存在"
}
```

## 备注
