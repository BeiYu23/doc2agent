# 创建单个区域仓

> warehouse.create — 创建单个区域仓

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建单个区域仓 |
| 文档地址 | `/docs/doudian/stock/stock-warehouse-create` |
| 接口 ID | `doudian.stock.warehouse.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/1855 |
| 更新日期 | `2020-11-29` |

## 接口说明

- 文档书: 库存API（版本 ）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 外部仓库ID，一个店铺下，同一个外部ID只能创建一个仓库 | `abc` |
| `name` | body | string | 是 | 仓库名称 | `test` |
| `intro` | body | string | 是 | 仓库介绍 | `test` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/create?app_key=your_appkey_here&method=warehouse.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | number | 仓库id | `6853386941874864391` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "6853386941874864391"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
