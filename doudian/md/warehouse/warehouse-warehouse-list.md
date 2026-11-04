# 批量查询区域仓

> warehouse.list — 批量查询区域仓

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量查询区域仓 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-warehouse-list` |
| 接口 ID | `doudian.warehouse.warehouse.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2079 |
| 更新日期 | `2022-06-23` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 否 | 外部仓库ID | `abc` |
| `warehouse_name` | body | string | 否 | 仓库名称 | `仓名称示例` |
| `addr` | body | object | 否 | 仓库覆盖地址 | `-` |
| `  └ addr_id1` | body | number | 是 | 一级地址 | `1` |
| `  └ addr_id2` | body | number | 否 | 二级地址 | `2` |
| `  └ addr_id3` | body | number | 否 | 三级地址 | `3` |
| `  └ addr_id4` | body | number | 否 | 四级地址 | `4` |
| `out_warehouse_ids` | body | array | 否 | 外部仓库ID列表 | `["1596011622", "1596011760"]` |
| `order_by` | body | string | 否 | 排序方式，可选create_time、update_time | `-` |
| `rank` | body | string | 否 | 顺序，可选desc、asc，与order_by同时生效 | `desc` |
| `page` | body | number | 是 | 页码，从0开始，最大到100 | `0` |
| `size` | body | number | 是 | 每页数量，最大100，超过100会限制到100 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/list?app_key=your_appkey_here&method=warehouse.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouses` | array | 仓库信息 | `-` |
| `total` | number | 总数 | `3` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2:参数错误,OrderBy格式不正确（sub_code: isv.business-failed:2） | 调整请求 |

## 响应示例

成功：

```json
{
  "data": {
    "total": "3",
    "warehouses": [
      {
        "addr": [
          {
            "addr_id1": "100",
            "addr_id2": "100100",
            "addr_id3": "100110",
            "addr_id4": "100111",
            "create_time": "1623918481",
            "update_time": "1623918481"
          }
        ],
        "address_detail": "xx小区xx号",
        "create_time": "1623918481",
        "intro": "介绍",
        "name": "名字",
        "out_fence_ids": "fence01",
        "out_warehouse_id": "ABC",
        "shop_id": "123456",
        "update_time": "1623918481",
        "warehouse_id": "6853386941874864391",
        "warehouse_location": {
          "address_id1": "11",
          "address_id2": "110000",
          "address_id3": "110101",
          "address_id4": "0"
        }
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2",
  "sub_msg": "2:参数错误,OrderBy格式不正确"
}
```

## 备注
