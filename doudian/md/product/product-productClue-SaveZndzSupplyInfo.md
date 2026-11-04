# 商机保存货源信息

> productClue.SaveZndzSupplyInfo — 商机保存货源信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商机保存货源信息 |
| 文档地址 | `/docs/doudian/product/product-productClue-SaveZndzSupplyInfo` |
| 接口 ID | `doudian.product.productClue.SaveZndzSupplyInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/productClue/SaveZndzSupplyInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7747 |
| 更新日期 | `2025-10-22` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_id` | body | mixed | 是 | 线索Id | `13637572` |
| `zndz_supply_info` | body | string | 是 | ISV对应货源以及货源保障信息.key为货源商品保障信息，value为货源商品id列表 | `{ 	"123": "2,1", 	"456": "1,3,2" }` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/productClue/SaveZndzSupplyInfo?app_key=your_appkey_here&method=productClue.SaveZndzSupplyInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 502:参数异常（sub_code: isv.business-failed:502） | 请联系管理员 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:502",
  "sub_msg": "502:参数异常"
}
```

## 备注
