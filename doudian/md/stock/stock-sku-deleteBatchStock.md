# sku.deleteBatchStock

> 批量删除批次库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.sku.deleteBatchStock` |
| 中文名 | 批量删除批次库存 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/deleteBatchStock` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/7723 |
| 更新日期 | `2025-08-26` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `items` | body | array | 否 | 删除item | `` |
| `  └ product_id` | body | mixed | 否 | 商品ID | `34543534` |
| `  └ sku_id` | body | mixed | 否 | skuid | `242342343` |
| `  └ warehouse_id` | body | mixed | 否 | 仓ID | `43242424` |
| `  └ batch_type` | body | mixed | 否 | 0时效 1唯一码 | `1` |
| `  └ time_batch_uk` | body | object | 否 | 时效唯一键 | `` |
| `    └ arrive_time_type` | body | mixed | 否 | 到货时间类型 | `2` |
| `    └ arrive_time` | body | mixed | 否 | 到货时间 | `12312321` |
| `  └ unique_batch_uk` | body | object | 否 | 唯一码唯一键 | `` |
| `    └ unique_id` | body | string | 否 | 唯一码id | `sfsafasdfdgd` |
| `  └ outer_id` | body | string | 否 | 入参区分 | `dsfsfsfsfd` |
| `token` | body | string | 否 | 单据幂等 | `asfsefdsfdsfsf` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/deleteBatchStock?app_key=your_appkey_here&method=sku.deleteBatchStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result_map` | string | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 该批次已删除（sub_code: isv.parameter-invalid:-10002） | 取消删除该批次 |

## 响应示例

成功：

```json
{
  "data": {
    "result_map": {}
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
  "sub_code": "isv.parameter-invalid:-10002",
  "sub_msg": "该批次已删除"
}
```

## 备注
