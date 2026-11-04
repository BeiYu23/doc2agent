# instantShopping.starhub.queryRelayReverseOrderStatus

> 逆向接力单状态查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.instantShopping.starhub.queryRelayReverseOrderStatus` |
| 中文名 | 逆向接力单状态查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6544 |
| 更新日期 | `2024-05-27` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `relay_order_id_list` | body | array | 否 | 抖音逆向接力单ID列表 | `["734672346823411"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.starhub.queryRelayReverseOrderStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `relay_reverse_order_status_map` | string | 逆向接力单数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法入参（sub_code: isv.parameter-invalid:40001） | 请传入合法入参 |
| `40004` | 非法的参数 / 没有权限操作逆向接力单（sub_code: isv.parameter-invalid:40006） | 请传入正确的逆向接力单id |

## 响应示例

成功：

```json
{
  "data": {
    "relay_reverse_order_status_map": {}
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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "非法入参"
}
```

## 备注
