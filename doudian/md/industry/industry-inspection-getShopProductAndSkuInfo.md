# inspection.getShopProductAndSkuInfo

> 查询商家的商品及其 SKU

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.getShopProductAndSkuInfo` |
| 中文名 | 查询商家的商品及其 SKU |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/getShopProductAndSkuInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8256 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id_list` | body | array | 否 | 商品 ID 列表 | `` |
| `product_name` | body | string | 否 | 商品名称（模糊匹配） | `` |
| `category_id_list` | body | array | 否 | 类目 ID | `["1000007628"]` |
| `brand_id_list` | body | array | 否 | 品牌 ID | `` |
| `is_for_sale` | body | boolean | 否 | 商品是否可售 | `true` |
| `page_size` | body | mixed | 否 | 每页大小 | `20` |
| `model_id_list` | body | array | 否 | 型号 ID | `` |
| `page` | body | mixed | 否 | 页码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/getShopProductAndSkuInfo?app_key=your_appkey_here&method=inspection.getShopProductAndSkuInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数 (如：operator_info 身份信息为空 或 operator_id 为空)（sub_code: isv.missing-parameter:-41003） | 请检查并传入必传参数 operator_info.operator_id |
| `40004` | 非法的参数 / 非法的参数 (如：分页参数 page 小于等于 0，或 page_size 不在 1~100 之间)（sub_code: isv.parameter-invalid:-41004） | 请检查并修正分页参数，确保 page > 0 且 0 < page_size <= 100 |
| `50002` | 业务处理失败 / 业务处理失败 (如：获取商品信息失败)（sub_code: isv.business-failed:-41005） | 请检查商品查询条件（如品类ID、品牌ID等）是否合法，或稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "product_list": [
        {
          "check_status": "3",
          "image_url": "xx",
          "product_id": "3816659558231834776",
          "product_name": "未拆封 Apple/苹果",
          "sku_list": [
            {
              "sku_id": "3664044248560898",
              "sku_name": "16GB+256GB/典雅黑",
              "sku_price": "300000",
              "spec_id": "1863612837722265"
            }
          ],
          "status": "0"
        }
      ],
      "total": "60"
    },
    "msg": ""
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:-41003",
  "sub_msg": "缺少必选参数 (如：operator_info 身份信息为空 或 operator_id 为空)"
}
```

## 备注
