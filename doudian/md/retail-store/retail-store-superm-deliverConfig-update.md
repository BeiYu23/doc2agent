# 时效管理更新

> superm.deliverConfig.update — 时效管理更新

| 元信息 | 值 |
| --- | --- |
| 中文名 | 时效管理更新 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-deliverConfig-update` |
| 接口 ID | `doudian.retail-store.superm.deliverConfig.update` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/deliverConfig/update` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3597 |
| 更新日期 | `2023-09-18` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `config_ids` | body | array | 是 | 配置ID列表 | `213432` |
| `shop_deliver_config` | body | object | 是 | 配置信息 | `` |
| `  └ deliver_type` | body | string | 否 | 配送类型 1：商家自行配置配送时长 2：系统自动计算配置时长 | `1` |
| `  └ normal_time_cost` | body | number | 否 | 三公里内常规时间配送时长（分钟） | `20` |
| `  └ special_time_list` | body | array | 否 | 三公里内特殊时段列表 | `` |
| `    └ start_time` | body | number | 是 | 时间片（单位秒，表示第几秒，如36000表示10:00） | `36000` |
| `    └ end_time` | body | number | 是 | 时间片（单位秒，表示第几秒，如39600表示11:00） | `39600` |
| `    └ time_cost` | body | number | 是 | 时间片内对应的配送时长（分钟） | `20` |
| `  └ over_limit_time_cost` | body | number | 否 | 三公里外每公里增加的配送时长（分钟） | `40` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/deliverConfig/update?app_key=your_appkey_here&method=superm.deliverConfig.update&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 时效配置查询失败（sub_code: isv.business-failed:202326） | 时效配置查询失败 |
| `50002` | 业务处理失败 / 当前店铺下未查询到该配置（sub_code: isv.business-failed:202327） | 当前店铺下未查询到该配置 |

## 响应示例

成功：

```json
{
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
