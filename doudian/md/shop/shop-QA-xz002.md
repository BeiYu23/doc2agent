# QA.xz002

> 接口描述11

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.QA.xz002` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/QA/xz002` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2494 |
| 更新日期 | `2022-09-15` |

## 接口说明

- 文档书: 店铺API（版本 V1.34）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_tag` | body | string | 是 | ppppp | `ppppp` |
| `tags` | body | array | 是 | ppppp | `ppppp` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/logisticsAddMultiPack?app_key=your_appkey_here&method=order.logisticsAddMultiPack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `custom_err` | object | ppppp | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "pack_list": [
      {
        "logistics_code": "111111111111111",
        "pack_id": "4705288465508532862",
        "shipped_order_info": [
          {
            "shipped_item_ids": "[\"123123\"]",
            "shipped_num": "1",
            "shipped_order_id": "123123"
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
