# product.setCargoStock

> 设置货品库存

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.stock.product.setCargoStock` |
| 中文名 | 设置货品库存 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/setCargoStock` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/34/8417 |
| 更新日期 | `2026-07-16` |

## 接口说明

- 文档书: 库存API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `items` | body | array | 否 | 设置的库存明细 | `` |
| `  └ stock_num` | body | mixed | 否 | 修改的库存数量 负数为减库存 正数为加库存 | `1` |
| `  └ cargo_id` | body | mixed | 否 | 货品ID | `123` |
| `  └ warehouse_code` | body | string | 否 | 仓编码 | `ABC` |
| `token` | body | string | 否 | 操作号 用于幂等 | `abcd` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/setCargoStock?app_key=your_appkey_here&method=product.setCargoStock&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `results` | array | 操作结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "results": [
      {
        "base_resp": {
          "status_code": "20001",
          "status_message": "系统错误"
        },
        "cargo_id": "123",
        "warehouse_code": "ABC"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
