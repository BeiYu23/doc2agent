# supplyChain.inspection.GetShopAvailableBaseInfo

> 查询商家可用的基础信息（类目、品牌、型号）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.inspection.GetShopAvailableBaseInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/8266 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 否 | 类目ID | `1000007628` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.GetShopAvailableBaseInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg` | string | 运行结果 | `success` |
| `data` | object | 类目信息 | `` |
| `code` | mixed | 执行编码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "available_category_list": [
        {
          "category_id": "1000007628",
          "category_name": "3C数码及配件",
          "children_category_list": [
            {}
          ]
        }
      ],
      "available_model_list": [
        {
          "model_id": "型号ID",
          "model_name": "型号名"
        }
      ],
      "shop_available_for_inspection_report": "true"
    },
    "msg": "success"
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
