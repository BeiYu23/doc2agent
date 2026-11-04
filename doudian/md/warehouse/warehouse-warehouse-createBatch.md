# warehouse.createBatch

> 批量创建区域仓

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.warehouse.createBatch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/createBatch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2076 |
| 更新日期 | `2022-06-23` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_list` | body | array | 是 | 外部仓信息列表 | `-` |
| `  └ out_warehouse_id` | body | string | 是 | 外部仓库ID，一个店铺下，同一个外部ID只能创建一个仓库 | `abc` |
| `  └ name` | body | string | 是 | 仓库名称 | `华北一仓` |
| `  └ intro` | body | string | 是 | 仓库介绍 | `这是一家外部仓` |
| `  └ address_detail` | body | string | 否 | 仓地址详细地址 | `xx区xx号` |
| `  └ warehouse_location` | body | object | 否 | 仓地址编码 | `` |
| `    └ address_id1` | body | number | 否 | 省地址编码 | `11` |
| `    └ address_id2` | body | number | 否 | 市地址编码 | `110000` |
| `    └ address_id3` | body | number | 否 | 区地址编码 | `110101` |
| `    └ address_id4` | body | number | 否 | 街道地址编码 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/createBatch?app_key=your_appkey_here&method=warehouse.createBatch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | key是outWarehouseId,value代表成功/失败 | `{         "qwb": true, // key是outWarehouseId         "qwb1": true // value代表成功/失败     },` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 仓库编码Z0010160524ZE02重复（sub_code: isv.business-failed:2） | 请检查仓库信息 |
| `50002` | 业务处理失败 / 单次请求过于频繁，请稍后重试（sub_code: isv.business-failed:1005） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {}
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
  "sub_msg": "仓库编码Z0010160524ZE02重复"
}
```

## 备注
