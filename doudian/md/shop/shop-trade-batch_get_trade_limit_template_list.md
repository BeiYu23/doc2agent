# 批量查询限购模板

> trade.batch_get_trade_limit_template_list — 批量查询限购模板

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量查询限购模板 |
| 文档地址 | `/docs/doudian/shop/shop-trade-batch_get_trade_limit_template_list` |
| 接口 ID | `doudian.shop.trade.batch_get_trade_limit_template_list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/batch_get_trade_limit_template_list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2112 |
| 更新日期 | `2022-08-15` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trade_limit_template_id_list` | body | array | 是 |  | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/batch_get_trade_limit_template_list?app_key=your_appkey_here&method=trade.batch_get_trade_limit_template_list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `trade_limit_template_list` | array | 运费模板ID列表 | `` |

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
        "channel_i_d": "",
        "channel_type": "",
        "shop_id": "1",
        "trade_limit_rule_list": [
          {
            "region_tree": {
              "code": ""
            },
            "time_period": {
              "time_period_fixed": {
                "cyclic": "0",
                "cyclic_option": {
                  "cyclic_interval": "0",
                  "cyclic_unit": "0",
                  "expire_time": "0",
                  "frequency": "0"
                },
                "end_time": "0",
                "start_time": "0"
              },
              "time_period_pattern": "0",
              "time_period_sliding_window": {
                "time_shift": "0",
                "window_size": "0"
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
                  "first_cid": "0",
                  "fourth_cid": "0",
                  "second_cid": "0",
                  "thrid_cid": "0"
                }
              ],
              "trade_limit_resource_id_list": "[\"1\"]"
            },
            "trade_limit_subject": "1"
          }
        ],
        "trade_limit_template_id": "0"
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
