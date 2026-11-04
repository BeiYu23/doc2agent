# sku.editCode

> 修改sku编码

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.sku.editCode` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/editCode` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/86 |
| 更新日期 | `2020-11-24` |

## 接口说明

- 文档书: 商品API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `code` | body | string | 否 | 编码 | `abc` |
| `sku_id` | body | number | 否 | skuid | `123246` |
| `out_sku_id` | body | number | 否 | 外部skuid | `32135135` |
| `product_id` | body | number | 否 | 商品id | `321545421545474` |
| `out_product_id` | body | number | 否 | 外部商品id | `3234156453136545` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sku/editCode?app_key=your_appkey_here&method=sku.editCode&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 系统错误:商品已删除，不可更新（sub_code: isv.parameter-invalid:7） | 请重新选择商品 |
| `40002` | 缺少必选参数 / 缺少sku_id参数（sub_code: isv.missing-parameter:4） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 找不到对应的sku（sub_code: isv.business-failed:5） | 请检查sku信息 |
| `50002` | 业务处理失败 / 2010401:请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 2010401:请求被限流, 请稍后再试 |
| `50002` | 业务处理失败 / 2010004:shopId: 196067705, 找不到对应的店铺（sub_code: isv.business-failed:2010004） | 2010004:shopId: 196067705, 找不到对应的店铺 |

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
  "sub_code": "isv.parameter-invalid:7",
  "sub_msg": "系统错误:商品已删除，不可更新"
}
```

## 备注
