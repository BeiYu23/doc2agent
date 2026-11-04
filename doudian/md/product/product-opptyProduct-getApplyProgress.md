# opptyProduct.getApplyProgress

> 机会品提报进度查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.opptyProduct.getApplyProgress` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/opptyProduct/getApplyProgress` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1796 |
| 更新日期 | `2021-09-13` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 是 | 商品ID | `123` |
| `origin` | body | string | 是 | 机会品来源。ISV代表服务商 | `ISV` |
| `type` | body | string | 是 | 机会品类型。NEW代表新品 | `NEW` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=opptyProduct.getApplyProgress&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status` | string | 机会品提报状态编码 | `NEW_PRODUCT` |
| `status_desc` | string | 机会品提报状态中文描述 | `新品` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "status": "NEW_PRODUCT",
    "status_desc": "新品"
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
