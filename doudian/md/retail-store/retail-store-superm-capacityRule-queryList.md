# superm.capacityRule.queryList

> 门店时段容量查询列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.capacityRule.queryList` |
| 中文名 | 门店时段容量查询列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3592 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_query` | body | object | 是 | 查询条件 | `` |
| `  └ rule_query` | body | object | 是 | 规则 | `` |
| `    └ rule_entity_type` | body | string | 是 | 规则归属类型 ，本期只有 1: 企业 | `1` |
| `    └ rule_name` | body | string | 否 | 规则名 | `test` |
| `    └ create_time_start` | body | number | 否 | 开始时间 秒级时间戳 | `1682059624` |
| `    └ create_time_end` | body | number | 否 | 结束时间 秒级时间戳 | `1682059624` |
| `    └ creator` | body | string | 否 | 创建人 | `xm` |
| `    └ status` | body | string | 否 | 规则状态，1启用，2不启用 | `1` |
| `    └ capacity_target_type` | body | string | 否 | 作业产能类型 本期只有 1:门店 | `1` |
| `    └ capacity_target_code` | body | array | 否 | 门店id | `12321312` |
| `  └ current_page` | body | string | 是 | 页码，从1计算 | `1` |
| `  └ page_size` | body | string | 是 | pageSize | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.capacityRule.queryList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `page_dto` | object | 查询到的实体信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 数据转换错误（sub_code: isv.business-failed:50202） | 数据转换错误 |
| `50002` | 业务处理失败 / 获取组织关系失败（sub_code: isv.business-failed:20232） | 获取组织关系失败 |
| `50002` | 业务处理失败 / 门店查询服务失败（sub_code: isv.business-failed:20233） | 门店查询服务失败 |

## 响应示例

成功：

```json
{
  "data": {
    "page_dto": {
      "current_page": "1",
      "page_size": "10",
      "rule_dtos": [
        {
          "relations": [
            {
              "capacity_target_code": "21343153",
              "capacity_target_type": "1",
              "rule_id": "Rule_34b55c75-3717"
            }
          ],
          "rule_dto": {
            "all_store": "1",
            "create_time": "1682059220",
            "creator": "xm",
            "date_limit_bound": "1",
            "date_limit_enable": "1",
            "rule_entity_type": "1",
            "rule_id": "Rule_34b55c75-3717",
            "rule_name": "test",
            "status": "1",
            "updater": "xm"
          }
        }
      ],
      "total_count": "99"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "参数错误"
}
```

## 备注
