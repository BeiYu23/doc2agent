# product.del

> 删除商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.del` |
| 中文名 | 删除商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/del` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/61 |
| 更新日期 | `2024-03-05` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 否 | 商品ID | `356545645645454` |
| `out_product_id` | body | mixed | 否 | 外部商品ID | `4156451` |
| `delete_forever` | body | boolean | 否 | 是否彻底删除 | `false` |
| `store_id` | body | string | 否 | 门店ID，不建议小时达一期用，即时零售单店版，无需使用 | `1111420330` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/del?app_key=your_appkey_here&method=product.del&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 商品删除失败: 【重复操作】商品操作重复，当前状态：删除（sub_code: isv.parameter-invalid:7） | 请重新选择商品 |
| `40004` | 非法的参数 / 根据out_product_id找不到商品信息（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010401:请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010013:获取店铺标签失败（sub_code: isv.business-failed:2010013） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010001:获取账号信息失败（sub_code: isv.business-failed:2010001） | 请检查参数后重试 |

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
  "sub_msg": "商品删除失败: 【重复操作】商品操作重复，当前状态：删除"
}
```

## 备注
