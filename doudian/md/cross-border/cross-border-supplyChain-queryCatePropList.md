# supplyChain.queryCatePropList

> 类目属性规则查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.supplyChain.queryCatePropList` |
| 中文名 | 类目属性规则查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryCatePropList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6323 |
| 更新日期 | `2024-04-26` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 类目id | `11111` |
| `item_type` | body | mixed | 否 | 货品类型 1:普通货品 | `1` |
| `bmp_code` | body | string | 是 | 行业身份（跨境pop：xiaodian.crossborder） | `xiaodian.crossborder` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/queryCatePropList?app_key=your_appkey_here&method=supplyChain.queryCatePropList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 内部服务返回错误（sub_code: isp.service-error:200001） | 请检查传入的参数并稍后重试 |
| `20000` | 系统错误 / 无权限（sub_code: isp.service-error:300001） | 请检查调用方身份信息并重试 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:400001） | 请检查传入的参数并重试 |
| `40002` | 缺少必选参数 / 缺少行业身份（sub_code: isv.missing-parameter:400002） | 请检查传入的 BmpCode 参数并重试 |
| `40004` | 非法的参数 / 行业身份不支持（sub_code: isv.parameter-invalid:400003） | 请检查传入的 BmpCode 参数并重试 |
| `20000` | 系统错误 / 查询类目属性错误（sub_code: isp.service-error:200011） | 请稍后重试 |
| `20000` | 系统错误 / 查询类目属性单位信息错误（sub_code: isp.service-error:200012） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "batch_prop_list": [
        {
          "prop_key": {
            "prop_code": "brand",
            "prop_key": "品牌",
            "prop_key_id": "111"
          },
          "prop_meta": {
            "customize": "false",
            "enumerable": "false",
            "is_required": "false",
            "max": "9999",
            "measure_unit_name": "毫米",
            "min": "1",
            "multi_choice": "false",
            "prop_type": "Common"
          },
          "prop_val": [
            {
              "prop_value": "是",
              "prop_value_id": "111"
            }
          ]
        }
      ],
      "category_prop_list": [
        {
          "prop_key": {
            "prop_code": "brand",
            "prop_key": "品牌",
            "prop_key_id": "111"
          },
          "prop_meta": {
            "customize": "false",
            "enumerable": "false",
            "is_required": "false",
            "max": "9999",
            "measure_unit_name": "毫米",
            "min": "1",
            "multi_choice": "false",
            "prop_type": "Common"
          },
          "prop_val": [
            {
              "prop_value": "是",
              "prop_value_id": "111"
            }
          ]
        }
      ],
      "period_prop_list": [
        {
          "prop_key": {
            "prop_code": "brand",
            "prop_key": "品牌",
            "prop_key_id": "111"
          },
          "prop_meta": {
            "customize": "false",
            "enumerable": "false",
            "is_required": "false",
            "max": "9999",
            "measure_unit_name": "毫米",
            "min": "1",
            "multi_choice": "false",
            "prop_type": "Common"
          },
          "prop_val": [
            {
              "prop_value": "是",
              "prop_value_id": "111"
            }
          ]
        }
      ],
      "sale_prop_list": [
        {
          "prop_key": {
            "prop_code": "brand",
            "prop_key": "品牌",
            "prop_key_id": "111"
          },
          "prop_meta": {
            "customize": "false",
            "enumerable": "false",
            "is_required": "false",
            "max": "9999",
            "measure_unit_name": "毫米",
            "min": "1",
            "multi_choice": "false",
            "prop_type": "Common"
          },
          "prop_val": [
            {
              "prop_value": "是",
              "prop_value_id": "111"
            }
          ]
        }
      ],
      "sku_category_prop_list": [
        {
          "prop_key": {
            "prop_code": "brand",
            "prop_key": "品牌",
            "prop_key_id": "111"
          },
          "prop_meta": {
            "customize": "false",
            "enumerable": "false",
            "is_required": "false",
            "max": "9999",
            "measure_unit_name": "毫米",
            "min": "1",
            "multi_choice": "false",
            "prop_type": "Common"
          },
          "prop_val": [
            {
              "prop_value": "是",
              "prop_value_id": "111"
            }
          ]
        }
      ]
    }
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:200001",
  "sub_msg": "内部服务返回错误"
}
```

## 备注
