# warehouse.bindFencesByStore

> 绑定门店和电子围栏

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.warehouse.bindFencesByStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/bindFencesByStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/2535 |
| 更新日期 | `2024-12-17` |

## 接口说明

- 文档书: 库存API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店id | `11114442321` |
| `add_out_fence_ids` | body | array | 是 | 要添加的外部围栏id列表 | `fence_id1,fence_id3` |
| `auto_opt` | body | boolean | 否 | 是否允许平台自动处理，默认不处理 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/bindFencesByStore?app_key=your_appkey_here&method=warehouse.bindFencesByStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2） | 检查参数 |
| `20000` | 系统错误 / 系统错误，请重试（sub_code: isp.service-error:9999） | 重试 |
| `50002` | 业务处理失败 / 该仓已绑定平台配送的围栏，不允许商家操作自配围栏（sub_code: isv.business-failed:100010） | 检查数据 |
| `50002` | 业务处理失败 / 围栏距离门店位置太远，要求围栏必须在门店50000 米内（sub_code: isv.business-failed:1009） | 检查数据 |
| `50002` | 业务处理失败 / 查询门店信息失败（sub_code: isv.business-failed:20004） | 重试 |
| `50002` | 业务处理失败 / 参数错误，请检查参数（sub_code: isv.business-failed:2122） | 只允许传入一个围栏，请检查 |
| `20000` | 系统错误 / 系统错误请重试（sub_code: isp.service-error:2129999） | 重试 |
| `20000` | 系统错误（sub_code: isp.service-error:20002） | 重试 |
| `50002` | 业务处理失败 / 不在系统约束的最大范围内（sub_code: isv.business-failed:2121006） | 缩小围栏 |

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
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "参数错误"
}
```

## 备注
