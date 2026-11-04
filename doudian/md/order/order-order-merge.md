# order.merge

> 判断一批待发货订单，哪些可以收件人信息一致，可以使用同一个包裹进行发货：
1. 批处理上限为100
2. 只支持近15天的代发货订单的合单判断
3. 同一天创建的订单：open_address_id不同的，一定不可以合单；open_address_id相同

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.merge` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/merge` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/4042 |
| 更新日期 | `2023-06-15` |

## 接口说明

- 文档书: 订单API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `merge_list` | body | array | 是 | 合并需求列表，最少支持2个，最多支持100个。order_id和open_address_id必须一一对应，不可传错 | `` |
| `  └ order_id` | body | string | 是 | 店铺订单id，不可重复。不支持售后单 | `12345678` |
| `  └ open_address_id` | body | string | 是 | 收件人唯一id，订单列表、订单详情及售后详情API会返回，长度256以内 | `#YOUR_SECRET_KEY` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/adjustInventory?app_key=your_appkey_here&method=yunc.adjustInventory&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_list` | array | 合单结果。可合单的订单ID列表用逗号分隔的字符串表示。比如，1111,2222表示订单1111和订单2222可合并发货，3333表示无法合单。 | `["1111,2222","3333"]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:100000） | 根据提示修改入参 |
| `50002` | 业务处理失败 / 内部错误，请重试（sub_code: isv.business-failed:200101） | 内部错误，请重试 |
| `80000` | 风控拦截 / 存在安全风险（sub_code: isv.risk-control-failed:300011） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "sub_code": "isv.parameter-invalid:100000",
  "sub_msg": "参数错误"
}
```

## 备注
