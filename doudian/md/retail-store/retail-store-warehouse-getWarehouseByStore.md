# warehouse.getWarehouseByStore

> 通过门店id查询仓信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.warehouse.getWarehouseByStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/getWarehouseByStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2442 |
| 更新日期 | `2023-05-30` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_ids` | body | array | 是 | 门店id列表 | `[1111410020,1111426012]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/getWarehouseByStore?app_key=your_appkey_here&method=warehouse.getWarehouseByStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_info_map` | string | 仓信息map | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2:参数错误,门店ID个数不得超过200（sub_code: isv.business-failed:2） | 无 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_info_map": {}
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2",
  "sub_msg": "2:参数错误,门店ID个数不得超过200"
}
```

## 备注
