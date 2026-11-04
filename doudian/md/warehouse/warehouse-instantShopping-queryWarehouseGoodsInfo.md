# instantShopping.queryWarehouseGoodsInfo

> 支持仓储服务商查询仓货品基础数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.instantShopping.queryWarehouseGoodsInfo` |
| 中文名 | 支持仓储服务商查询仓货品基础数据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6405 |
| 更新日期 | `2024-04-12` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `goods_ids` | body | array | 是 | 抖音给到的货品ID | `["1","2"]` |
| `warehouse_id` | body | string | 是 | 抖音给到的仓ID | `"1"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.queryWarehouseGoodsInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_goods_info_list` | array | 货品结果List | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参不正确（sub_code: isv.parameter-invalid:40001） | 调整为正确入参 |
| `40004` | 非法的参数 / 权限不正确（sub_code: isv.parameter-invalid:40006） | 查询有权限的数据 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_goods_info_list": [
      {
        "category_detail": {
          "first_c_name": "\"一级类目节点名称\"",
          "first_cid": "1",
          "fourth_c_name": "\"四级类目节点名称\"",
          "fourth_cid": "4",
          "second_c_name": "\"二级类目节点名称\"",
          "second_cid": "2",
          "third_c_name": "\"三级类目节点名称\"",
          "third_cid": "3"
        },
        "goods_bar_code_list": "[\"111\",\"222\"]",
        "goods_id": "\"1234334\"",
        "goods_name": "\"樱桃\"",
        "gross_height": "124",
        "gross_length": "112",
        "gross_weight": "1256",
        "gross_width": "233",
        "net_height": "323",
        "net_length": "111",
        "net_weight": "123",
        "net_width": "232",
        "org_shop_id": "\"2234\"",
        "sku_spec_name": [
          {
            "name": "\"重量\"",
            "value": "\"2斤\""
          }
        ],
        "temperature_layer": "1"
      }
    ]
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
  "sub_msg": "入参不正确"
}
```

## 备注
