# orderCode.getOrderCodeDetail

> 通过订单码和商家信息查询订单码绑定的订单详情信息(包括材质、镶嵌材质、质量、商品名称等)

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bic-inspect.orderCode.getOrderCodeDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/getOrderCodeDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/51/2857 |
| 更新日期 | `2024-07-30` |

## 接口说明

- 文档书: BIC质检API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orderCodes` | body | array | 是 | 订单码列表，最多支持50个订单码一起查询，超过50个取前50个订单码 | `[     "0117457223",     "0402702663",     "0738431303",     "1006866759"   ]` |
| `shopId` | body | number | 是 | 店铺ID | `1111228346` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt/2?app_key=your_appkey_here&method=test.encrypt.2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_id` | number | 店铺ID | `1111228346` |
| `shop_name` | string | 店铺名称 | `订单测试店铺` |
| `order_detail_list` | array | 订单明细列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 入参为空（sub_code: isv.missing-parameter:20001） | 入参不能为空，填入合法参数 |
| `50002` | 业务处理失败 / 订单查询失败（sub_code: isv.business-failed:20002） | 不是qic商家 |
| `40004` | 非法的参数 / 当前商家不是ERP商家（sub_code: isv.parameter-invalid:20005） | 当前商家不是ERP商家 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:20004） | 订单不存在 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "2",
    "or": "7"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:20001",
  "sub_msg": "入参为空"
}
```

## 备注
