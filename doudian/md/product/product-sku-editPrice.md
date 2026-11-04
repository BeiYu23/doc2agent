# sku.editPrice

> 编辑sku价格

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.sku.editPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sku/editPrice` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1822 |
| 更新日期 | `2024-03-05` |

## 接口说明

- 文档书: 商品API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `price` | body | mixed | 是 | 售价 (单位 分) | `3200` |
| `code` | body | string | 否 | sku编码 | `aaa` |
| `sku_id` | body | mixed | 否 | skuid | `1233245` |
| `out_sku_id` | body | mixed | 否 | 外部skuid | `132345654` |
| `product_id` | body | string | 否 | 商品id | `322315645454655` |
| `out_product_id` | body | mixed | 否 | 外部商品id | `2634786238745687465` |
| `store_id` | body | string | 否 | 即时零售连锁版，通过传入主品id+门店id对该门店下的子品进行操作，即时零售单店版，无需使用 | `12345` |

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
| `40004` | 非法的参数 / 系统错误:商品已删除，不可更新（sub_code: isv.parameter-invalid:7） | 请重新选择商品 |
| `40004` | 非法的参数 / sku_id: 17040531912765881, 找不到对应的sku（sub_code: isv.parameter-invalid:5） | 请检查参数后重试 |
| `40004` | 非法的参数 / out_sku_id错误, 无法定位到sku（sub_code: isv.parameter-invalid:4） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 2010401:请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 请稍后再试 |
| `50002` | 业务处理失败 / 2010013:获取账号信息失败（sub_code: isv.business-failed:2010013） | 请稍后再试 |
| `50002` | 业务处理失败 / 2010001:查询关联productId信息失败（sub_code: isv.business-failed:2010001） | 2010001:查询关联productId信息失败 |

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
