# 门店绑定运费模版

> shop.bindStoreFreight — 门店绑定运费模版

| 元信息 | 值 |
| --- | --- |
| 中文名 | 门店绑定运费模版 |
| 文档地址 | `/docs/doudian/shop/shop-shop-bindStoreFreight` |
| 接口 ID | `doudian.shop.shop.bindStoreFreight` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/bindStoreFreight` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2381 |
| 更新日期 | `2024-02-26` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店ID | `123` |
| `freight_id` | body | mixed | 是 | 运费模版ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:1） | 检查下参数 |
| `50002` | 业务处理失败 / 2:获取模版信息失败（sub_code: isv.business-failed:2） | 2:获取模版信息失败 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1",
  "sub_msg": "参数异常"
}
```

## 备注
