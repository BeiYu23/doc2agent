# warehouse.getWarehouseByStore

> 通过门店id查询仓信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.warehouse.getWarehouseByStore` |
| 中文名 | 通过门店id查询仓信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/getWarehouseByStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2423 |
| 更新日期 | `2022-08-25` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 |  | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/getWarehouseByStore?app_key=your_appkey_here&method=warehouse.getWarehouseByStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_info_list` | array |  | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_info_list": [
      {
        "address_detail": "",
        "create_time": "0",
        "introduction": "",
        "name": "",
        "out_fence_ids": "[]",
        "out_warehouse_id": "",
        "shop_id": "0",
        "update_time": "0",
        "warehouse_id": "0",
        "warehouse_location": {
          "address_id1": "0",
          "address_id2": "0",
          "address_id3": "0",
          "address_id4": "0",
          "address_name1": "",
          "address_name2": "",
          "address_name3": "",
          "address_name4": ""
        },
        "warehouse_type": "0"
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
