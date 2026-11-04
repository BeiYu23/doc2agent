# product.changeSupplyCargoBind

> 变更库存供给关系

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.product.changeSupplyCargoBind` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/changeSupplyCargoBind` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8330 |
| 更新日期 | `2026-05-22` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `req_list` | body | array | 否 | 入参列表 | `` |
| `  └ sale_product` | body | object | 否 | 前台销售品 | `` |
| `    └ sku_id` | body | mixed | 否 | 销售商品skuid | `3659238057270815` |
| `    └ product_id` | body | mixed | 否 | 销售商品id | `3820739174718380278` |
| `  └ change_type` | body | mixed | 否 | 1:设置；2-删除 | `1` |
| `  └ outer_id` | body | string | 否 | 操作号id，做结果映射使用 | `a123` |
| `  └ supply_cargo` | body | object | 否 | 供货品 | `` |
| `    └ cargo_id` | body | mixed | 否 | 供货商品id | `3820584917637660673` |
| `    └ cargo_sku_id` | body | mixed | 否 | 供货商品skuid | `3659238054343021` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/changeSupplyCargoBind?app_key=your_appkey_here&method=product.changeSupplyCargoBind&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `resp_list` | array | 操作结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:-10007） | 根据报错文案调整入参 |

## 响应示例

成功：

```json
{
  "data": {
    "resp_list": [
      {
        "base_resp": {
          "status_code": "12000128",
          "status_message": "商品绑定数量超出限制"
        },
        "outer_id": "a123"
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
  "sub_code": "isv.parameter-invalid:-10007",
  "sub_msg": "非法参数"
}
```

## 备注
