# supplyChain.batchGetCargoDetail

> 批量获取货品详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.supplyChain.batchGetCargoDetail` |
| 中文名 | 批量获取货品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/batchGetCargoDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6322 |
| 更新日期 | `2024-03-26` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cargo_codes` | body | array | 是 | 货品编码 | `7337822801686511916` |
| `bmp_code` | body | string | 否 | 业务身份编码 | `xiaodian.crossborder` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/batchGetCargoDetail?app_key=your_appkey_here&method=supplyChain.batchGetCargoDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "batch_props": [
          {
            "is_multi": "true",
            "prop_key": {
              "prop_code": "birth_batch",
              "prop_key": "生产批号",
              "prop_key_id": "283"
            },
            "prop_val": {
              "prop_value": "是",
              "prop_value_id": "227"
            },
            "prop_val_list": [
              {
                "prop_value": "是",
                "prop_value_id": "227"
              }
            ]
          }
        ],
        "cargo_category_id": "22291",
        "cargo_code": "7337822801686511916",
        "cargo_name": "测试货品",
        "category_props": [
          {
            "is_multi": "true",
            "prop_key": {
              "prop_code": "brand",
              "prop_key": "品牌",
              "prop_key_id": "292"
            },
            "prop_val": {
              "prop_value": "测试品牌",
              "prop_value_id": "286890612"
            },
            "prop_val_list": [
              {
                "prop_value": "测试品牌",
                "prop_value_id": "286890612"
              }
            ]
          }
        ],
        "desc": "测试新建货品",
        "flatten_status": "3",
        "is_need_batch": "1",
        "is_need_valid": "1",
        "period_props": [
          {
            "is_multi": "true",
            "prop_key": {
              "prop_code": "period_of_validity",
              "prop_key": "有效期",
              "prop_key_id": "280"
            },
            "prop_val": {
              "prop_value": "100",
              "prop_value_id": "1"
            },
            "prop_val_list": [
              {
                "prop_value": "100",
                "prop_value_id": "1"
              }
            ]
          }
        ],
        "picture": "https://xxx.png",
        "product_sub_pictures": "https://xxx.png",
        "sku_category_props": [
          {
            "is_multi": "true",
            "prop_key": {
              "prop_code": "barcode",
              "prop_key": "条形码",
              "prop_key_id": "286"
            },
            "prop_val": {
              "prop_value": "979624064913",
              "prop_value_id": "1"
            },
            "prop_val_list": [
              {
                "prop_value": "979624064913",
                "prop_value_id": "1"
              }
            ]
          }
        ],
        "sku_image": "https://xxx.png",
        "sku_props": [
          {
            "prop_key": {
              "prop_code": "specs",
              "prop_key": "规格",
              "prop_key_id": "330"
            },
            "prop_val": {
              "prop_value": "50ml",
              "prop_value_id": "1"
            }
          }
        ]
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
