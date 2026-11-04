# 查询区域仓

> warehouse.info — 查询区域仓

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询区域仓 |
| 文档地址 | `/docs/doudian/shop/shop-warehouse-info` |
| 接口 ID | `doudian.shop.warehouse.info` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/info` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2077 |
| 更新日期 | `2022-07-12` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 仓库编码 | `ABC` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/info?app_key=your_appkey_here&method=warehouse.info&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 仓库信息 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 仓库不存在（sub_code: isv.business-failed:20002） | 仓库不存在,请检查信息 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "addr": [
        {
          "addr_id1": "1",
          "addr_id2": "2",
          "addr_id3": "3",
          "addr_id4": "4",
          "create_time": "1624245280",
          "update_time": "1624245280"
        }
      ],
      "address_detail": "\"\"",
      "create_time": "1624245280",
      "intro": "介绍测试",
      "name": "名称测试",
      "out_warehouse_id": "ABC",
      "shop_id": "95250",
      "update_time": "1624245280",
      "warehouse_id": "6152361283123",
      "warehouse_location": {
        "address_id1": "11",
        "address_id2": "110000",
        "address_id3": "110101",
        "address_id4": "0",
        "address_name1": "北京市",
        "address_name2": "北京市",
        "address_name3": "东城区",
        "address_name4": "\"\""
      }
    }
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
  "sub_code": "isv.business-failed:20002",
  "sub_msg": "仓库不存在"
}
```

## 备注
