# bigCustomer.queryCounting

> 查询统计销量结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.bigCustomer.queryCounting` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/bigCustomer/queryCounting` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7650 |
| 更新日期 | `2025-07-31` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `items` | body | array | 是 | 查询列表（size <= 200） | `` |
| `  └ product_id` | body | number | 是 | 平台商品ID | `3672279718683607404` |
| `  └ sku_id` | body | number | 是 | 平台SkuId | `3453363154713090` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/callback?app_key=your_appkey_here&method=logistics.callback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 计数返回结果 | `` |

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
