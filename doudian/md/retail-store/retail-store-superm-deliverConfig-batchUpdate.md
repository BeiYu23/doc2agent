# 小时达店铺配送配置批量更新

> superm.deliverConfig.batchUpdate — 小时达店铺配送配置批量更新

| 元信息 | 值 |
| --- | --- |
| 中文名 | 小时达店铺配送配置批量更新 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-deliverConfig-batchUpdate` |
| 接口 ID | `doudian.retail-store.superm.deliverConfig.batchUpdate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/5270 |
| 更新日期 | `2023-10-23` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `batch_update_shop_deliver_config_req` | body | array | 是 | 更新后的配置数据 | `` |
| `  └ config_id` | body | number | 是 | 配置ID列表 从YOUR_SECRET_KEY | `1001` |
| `  └ shop_deliver_config` | body | object | 是 | 门店配送配置 | `` |
| `    └ deliver_type` | body | string | 否 | 配送类型 1：商家自行配置配送时长 2：系统自动计算配置时长 | `1` |
| `    └ normal_time_cost` | body | number | 否 | 三公里内常规时间配送时长（分钟） | `40` |
| `    └ special_time_list` | body | array | 否 | 三公里内特殊时段列表 | `` |
| `      └ start_time` | body | number | 是 | 时间片（单位秒，表示第几秒，如36000表示10:00） | `200` |
| `      └ end_time` | body | number | 是 | 时间片（单位秒，表示第几秒，如39600表示11:00） | `400` |
| `      └ time_cost` | body | number | 是 | 时间片内对应的配送时长（分钟） | `500` |
| `    └ over_limit_time_cost` | body | number | 否 | 三公里外每公里增加的配送时长（分钟） | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.deliverConfig.batchUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `failed_config_ids` | array | 更新失败的配置id | `[166,23,41]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `40004` | 非法的参数 / 参数转换错误（sub_code: isv.parameter-invalid:50202） | 参数转换错误 |
| `50002` | 业务处理失败 / 时效配置查询失败（sub_code: isv.business-failed:202326） | 时效配置查询失败 |
| `50002` | 业务处理失败 / 时效配置查询失败（sub_code: isv.business-failed:202327） | 时效配置查询失败 |
| `50002` | 业务处理失败 / 更新店铺送达时长配置信息失败（sub_code: isv.business-failed:10110） | 更新店铺送达时长配置信息失败 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_config_ids": "[166,23,41]"
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
