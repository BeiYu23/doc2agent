# sms.audience.listCrowdTask

> 获取种子人群任务列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.audience.listCrowdTask` |
| 中文名 | 获取种子人群任务列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/listCrowdTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7658 |
| 更新日期 | `2025-09-11` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `crowd_task_id` | body | mixed | 否 | 人群任务id | `123` |
| `crowd_type` | body | mixed | 是 | 已废弃，可设置成0实际不生效。建议使用新字段支持多选：crowd_type_list | `2` |
| `page_index` | body | mixed | 是 | 页码 | `0` |
| `page_size` | body | mixed | 是 | 页大小 | `10` |
| `crowd_name` | body | string | 否 | 人群名称 | `test` |
| `crowd_type_list` | body | array | 否 | 人群任务类型 2-种子人群 3-规则圈选人群 4-行为圈群 | `[2,3]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.listCrowdTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `crowd_task_list` | array | 人群任务列表 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:10001） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "crowd_task_list": [
      {
        "app_id": "10",
        "cate_ids": [
          {
            "first_cid": "200001",
            "second_cid": "210002"
          }
        ],
        "crowd_id": "test",
        "crowd_name": "test",
        "crowd_task_id": "10",
        "crowd_task_status_info": {
          "crowd_count": "10",
          "crowd_task_status": "10",
          "last_update_time": "10"
        },
        "crowd_type": "1",
        "exclude_seed": "false",
        "id_type": "1",
        "lookalike_count": "10",
        "seed_rule_period": "test",
        "seed_rule_type": "test",
        "seed_source": "test",
        "seed_type": "test",
        "shop_id": "10",
        "target_type": "test",
        "target_type_period": "test",
        "tos_url": "test"
      }
    ],
    "total": "10"
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
  "sub_code": "isv.business-failed:10001",
  "sub_msg": "业务处理失败"
}
```

## 备注
