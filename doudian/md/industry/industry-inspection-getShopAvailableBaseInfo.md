# 查询商家可用的基础信息（类目、品牌、型号

> inspection.getShopAvailableBaseInfo — 查询商家可用的基础信息（类目、品牌、型号）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询商家可用的基础信息（类目、品牌、型号 |
| 文档地址 | `/docs/doudian/industry/industry-inspection-getShopAvailableBaseInfo` |
| 接口 ID | `doudian.industry.inspection.getShopAvailableBaseInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/getShopAvailableBaseInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8255 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/getShopAvailableBaseInfo?app_key=your_appkey_here&method=inspection.getShopAvailableBaseInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 相应数据 | `` |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数 (如：operator_info 身份信息为空 或 operator_id 为空)（sub_code: isv.missing-parameter:-41003） | 请检查并传入必传参数 operator_info.operator_id |
| `50002` | 业务处理失败 / 业务处理失败 (如：获取店铺基础信息失败)（sub_code: isv.business-failed:-41005） | 请检查传入的参数（如 category_id）是否有效，或稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "available_category_list": [
        {
          "category_id": "1000007020",
          "category_name": "3C数码及配件",
          "children_category_list": [
            {}
          ]
        }
      ],
      "available_model_list": [
        {
          "model_id": "88",
          "model_name": "E2"
        }
      ],
      "shop_available_for_inspection_report": "true"
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
