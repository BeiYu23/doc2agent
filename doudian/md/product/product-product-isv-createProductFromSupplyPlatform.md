# product.isv.createProductFromSupplyPlatform

> 搜索线索提报 (三方货源发品场景)

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.isv.createProductFromSupplyPlatform` |
| 中文名 | 搜索线索提报 (三方货源发品场景 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isv/createProductFromSupplyPlatform` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4665 |
| 更新日期 | `2023-09-07` |

## 接口说明

- 文档书: 商品API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query_id` | body | string | 否 | 搜索词id | `"qwe14"` |
| `product_id` | body | number | 是 | 商品id | `123445234234344` |
| `origin` | body | string | 是 | 来源 | `2` |
| `clue_id` | body | number | 否 | 线索id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/isv/createProductFromSupplyPlatform?app_key=your_appkey_here&method=product.isv.createProductFromSupplyPlatform&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:501） | 联系开发者 |
| `40004` | 非法的参数 / clueId和queryId不能同时为空（sub_code: isv.parameter-invalid:502） | clueId>0 或者 queryId不为空字符串 |
| `40004` | 非法的参数 / 平台来源错误（sub_code: isv.parameter-invalid:503） | 联系开发者 |
| `40004` | 非法的参数 / ProductId不能为0（sub_code: isv.parameter-invalid:504） | ProductId>0 |
| `50002` | 业务处理失败 / 无效的线索信息（sub_code: isv.business-failed:505） | 联系开发者 |
| `50002` | 业务处理失败 / 无效商品id（sub_code: isv.business-failed:506） | 联系开发者 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:501",
  "sub_msg": "系统异常"
}
```

## 备注
