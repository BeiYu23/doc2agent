# btas.getInspectionOrder

> ⁣商家_查询订单的质检信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.getInspectionOrder` |
| 中文名 | ⁣商家_查询订单的质检信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/getInspectionOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/473 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 父订单（店铺单）编号 | `4775168038676399798` |
| `order_code` | body | string | 否 | 订单码，与店铺单ID二选一。 | `052131231222` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_id` | string | 父订单（店铺单）编号 | `"4775168038676399798"` |
| `product_orders` | array | 商品单内容，根据订单ID查可能返回多条数据，根据orderCode查仅有一条数据。 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:4000） | 确认订单编码是否正确 |
| `50002` | 业务处理失败 / 2030:参数错误（sub_code: isv.business-failed:2030） | 检查订单号 |
| `50002` | 业务处理失败 / 4008:获取商品件单出错，请重试（sub_code: isv.business-failed:4008） | 4008:获取商品件单出错，请重试 |

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
  "sub_code": "isv.business-failed:4000",
  "sub_msg": "订单不存在"
}
```

## 备注
