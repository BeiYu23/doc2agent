# 查询备货入库子单状态

> instantShopping.queryStockUpInboundOrder — 查询备货入库子单状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询备货入库子单状态 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-instantShopping-queryStockUpInboundOrder` |
| 接口 ID | `doudian.warehouse.instantShopping.queryStockUpInboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6755 |
| 更新日期 | `2024-08-08` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `stock_up_sub_order_id_list` | body | array | 是 | 抖音备货入库子单ID列表 上限20个 | `["12312411241245124"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.queryStockUpInboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sub_order_map` | string | Key:抖音子单ID Value: 子单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误（sub_code: isv.parameter-invalid:ReqParamsInvalid） | 检查参数正确性 |

## 响应示例

成功：

```json
{
  "data": {
    "sub_order_map": {}
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
  "sub_code": "isv.parameter-invalid:ReqParamsInvalid",
  "sub_msg": "入参错误"
}
```

## 备注
