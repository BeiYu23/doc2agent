# 设置指定地址下的仓的优先级

> warehouse.setPriority — 设置指定地址下的仓的优先级

| 元信息 | 值 |
| --- | --- |
| 中文名 | 设置指定地址下的仓的优先级 |
| 文档地址 | `/docs/doudian/stock/stock-warehouse-setPriority` |
| 接口 ID | `doudian.stock.warehouse.setPriority` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/setPriority` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/1863 |
| 更新日期 | `2020-11-29` |

## 接口说明

- 文档书: 库存API（版本 ）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `addr` | body | object | 是 | 配送地址 | `-` |
| `  └ addr_id1` | body | number | 是 | 一级地址id | `100` |
| `  └ addr_id2` | body | number | 否 | 二级地址id | `100100` |
| `  └ addr_id3` | body | number | 否 | 三级地址id | `100110` |
| `  └ addr_id4` | body | number | 否 | 四级地址id | `100111` |
| `priorities` | body | string | 是 | 前面是out_warehouse_id，后面是仓优先级 仓优先级，0-5，0优先级最高，5最低 | `{"123213":0,"123214":1}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/setPriority?app_key=your_appkey_here&method=warehouse.setPriority&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
