# superm.capacityRule.queryByid

> 门店时段容量查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.capacityRule.queryByid` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3593 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `rule_id` | body | string | 是 | 规则id | `Rule-124121` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.capacityRule.queryByid&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `rule_dto` | object | 查询到的实体信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 获取组织关系失败（sub_code: isv.business-failed:20232） | 获取组织关系失败 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 门店查询服务失败（sub_code: isv.business-failed:20233） | 门店查询服务失败 |
| `10001` | 请求部分失败 / 数据转换错误（sub_code: isv.business-part-failed:50202） | 数据转换错误 |

## 响应示例

成功：

```json
{
  "data": {
    "rule_dto": {
      "details": [
        {
          "end_date": "2022-06-17",
          "end_time": "19:00",
          "rule_id": "Rule-124121",
          "start_date": "2022-06-17",
          "start_time": "19:00",
          "time_interval": "60",
          "time_limit_bound": "1"
        }
      ],
      "relations": [
        {
          "capacity_target_code": "21421321",
          "capacity_target_type": "1",
          "rule_id": "Rule-124121"
        }
      ],
      "rule_dto": {
        "all_store": "1",
        "create_time": "1682059220",
        "creator": "xm",
        "date_limit_bound": "1",
        "date_limit_enable": "1",
        "rule_entity_type": "1",
        "rule_id": "Rule-124121",
        "rule_name": "test",
        "status": "1",
        "updater": "xm"
      }
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:20232",
  "sub_msg": "获取组织关系失败"
}
```

## 备注
