# trade.batchGetTradeLimitTemplateList

> 批量查询限购模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.trade.batchGetTradeLimitTemplateList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/batchGetTradeLimitTemplateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2438 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trade_limit_template_id_list` | body | array | 是 | 限购模板ID列表 | `7130507373692584001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/batchGetTradeLimitTemplateList?app_key=your_appkey_here&method=trade.batchGetTradeLimitTemplateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `trade_limit_template_list` | array | 限购模板信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "trade_limit_template_list": [
      {
        "shop_id": "9041",
        "trade_limit_rule_list": [
          {
            "time_period": {
              "time_period_fixed": {
                "cyclic": "false",
                "cyclic_option": {
                  "cyclic_interval": "1",
                  "cyclic_unit": "1",
                  "expire_time": "100",
                  "frequency": "1"
                },
                "end_time": "1660745000",
                "start_time": "1660742928"
              },
              "time_period_pattern": "1",
              "time_period_sliding_window": {
                "time_shift": "0",
                "window_size": "100"
              }
            },
            "trade_limit_model": "1",
            "trade_limit_pattern": {
              "cumulative_max": "10",
              "maximum": "5",
              "minimum": "1"
            },
            "trade_limit_resource": "1",
            "trade_limit_resource_object": {
              "product_category_list": [
                {
                  "first_cid": "1",
                  "fourth_cid": "4",
                  "second_cid": "2",
                  "thrid_cid": "3"
                }
              ],
              "trade_limit_resource_id_list": "[\"1\"]"
            },
            "trade_limit_subject": "1"
          }
        ],
        "trade_limit_template_id": "7130507373692584000"
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
