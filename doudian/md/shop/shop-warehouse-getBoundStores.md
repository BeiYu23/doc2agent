# warehouse.getBoundStores

> 获取仓库已经绑定的列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.warehouse.getBoundStores` |
| 中文名 | 获取仓库已经绑定的列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/getBoundStores` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2074 |
| 更新日期 | `2022-08-09` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_name` | body | string | 否 | 指定门店名称查询，可模糊查询 | `门店1` |
| `store_id` | body | array | 否 | 指定定门店id查询 | `123` |
| `page_info` | body | object | 是 | 翻页信息 | `` |
| `  └ page` | body | number | 是 | 从0开始 | `0` |
| `  └ page_size` | body | number | 是 | 最大200 | `页面大小` |
| `out_warehouse_id` | body | string | 是 | 外部仓id | `id1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/getBoundStores?app_key=your_appkey_here&method=warehouse.getBoundStores&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_stores` | array | 仓绑定的门店信息 | `` |
| `total` | number | 绑定门店总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "total": "100",
    "warehouse_stores": [
      {
        "is_valid": "true",
        "store_id": "123",
        "store_name": "门店1"
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
