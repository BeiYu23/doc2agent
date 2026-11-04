# superm.deliverConfig.queryList

> 时效管理查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.deliverConfig.queryList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3596 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_ids` | body | array | 否 | 店铺id列表，不传则查门店下的配置 | `23423143412` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.deliverConfig.queryList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_deliver_config_list` | array | 配置列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 时效配置查询失败（sub_code: isv.business-failed:202326） | 时效配置查询失败 |
| `50002` | 业务处理失败 / 当前店铺下未查询到该配置（sub_code: isv.business-failed:202327） | 当前店铺下未查询到该配置 |
| `50002` | 业务处理失败 / 数据转换错误（sub_code: isv.business-failed:50202） | 数据转换错误 |
| `50002` | 业务处理失败 / 门店查询服务失败（sub_code: isv.business-failed:20233） | 门店查询服务失败 |

## 响应示例

成功：

```json
{
  "data": {
    "shop_deliver_config_list": [
      {
        "config_id": "32133123",
        "config_status": "2",
        "config_type": "1",
        "deliver_type": "1",
        "is_pre_check_suc": "true",
        "normal_time_cost": "20",
        "over_limit_time_cost": "40",
        "pre_check_msg": "true",
        "shop_id": "342543534",
        "special_time_list": [
          {
            "end_time": "39600",
            "start_time": "36000",
            "time_cost": "20"
          }
        ],
        "store_id": "2424123",
        "update_time": "2023-02-13 20:06:31"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "参数错误"
}
```

## 备注
