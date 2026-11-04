# yunc.shopWarehouseRefQuery

> 商家入驻仓关系查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.shopWarehouseRefQuery` |
| 中文名 | 商家入驻仓关系查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/shopWarehouseRefQuery` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/925 |
| 更新日期 | `2022-08-31` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id` | body | number | 是 | 店铺id | `1001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/shopWarehouseRefQuery?app_key=your_appkey_here&method=yunc.shopWarehouseRefQuery&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_list` | array | 仓信息 | `` |
| `owner_code` | string | 货主编码 | `货主code` |
| `owner_name` | string | 货主名称 | `货主名称` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 3000:参数错误（sub_code: isv.business-failed:3000） | 校验参数准确性 |

## 响应示例

成功：

```json
{
  "data": {
    "owner_code": "货主code",
    "owner_name": "货主名称",
    "warehouse_list": [
      {
        "warehouse_code": "W01",
        "warehouse_name": "瑞丽测试仓"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:3000",
  "sub_msg": "3000:参数错误"
}
```

## 备注
