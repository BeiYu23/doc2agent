# 绑定单个地址到区域仓

> warehouse.setAddr — 绑定单个地址到区域仓

| 元信息 | 值 |
| --- | --- |
| 中文名 | 绑定单个地址到区域仓 |
| 文档地址 | `/docs/doudian/stock/stock-warehouse-setAddr` |
| 接口 ID | `doudian.stock.warehouse.setAddr` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/setAddr` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/1859 |
| 更新日期 | `2020-11-29` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 外部仓库ID | `abc` |
| `addr` | body | object | 是 | 仓库地址 | `-` |
| `  └ addr_id1` | body | number | 是 | 一级地址 | `一级地址` |
| `  └ addr_id2` | body | number | 否 | 二级地址 | `二级地址` |
| `  └ addr_id3` | body | number | 否 | 三级地址 | `三级地址` |
| `  └ addr_id4` | body | number | 否 | 四级地址 | `四级地址` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/setAddr?app_key=your_appkey_here&method=warehouse.setAddr&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2:参数错误:110000-110101-0-0地址格式错误（sub_code: isv.business-failed:2） | 请检查地址格式 |
| `50002` | 业务处理失败 / 20002:仓库不存在（sub_code: isv.business-failed:20002） | 请检查仓库id信息 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2",
  "sub_msg": "2:参数错误:110000-110101-0-0地址格式错误"
}
```

## 备注
