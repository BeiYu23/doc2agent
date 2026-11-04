# 查询发布单列表

> openCloud.deployTicket.list — 查询发布单列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询发布单列表 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-deployTicket-list` |
| 接口 ID | `doudian.cloud.openCloud.deployTicket.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/deployTicket/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/6450 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | mixed | 否 | 起始时间 | `1712160000000` |
| `end_time` | body | mixed | 否 | 截止时间 | `1712764799999` |
| `cs_id` | body | string | 否 | 容器服务ID | `7345699782717079843` |
| `ticket_type` | body | mixed | 否 | 发布单类型：0 正常发布；1 重启发布；2 回滚发布 | `0` |
| `ticket_status` | body | mixed | 否 | 发布单状态：5 待审批；6 审批失败；10 待部署；20 部署中；98 取消发布；99 部署失败；100 部署成功；110 已回滚 | `100` |
| `volc_account_id` | body | mixed | 否 | 火山账号ID。如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100003854` |
| `page_index` | body | mixed | 是 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每页数量，最大100 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/deployTicket/list?app_key=your_appkey_here&method=openCloud.deployTicket.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tickets` | array | 发布单列表 | `` |
| `total` | mixed | 发布单总数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "tickets": [
      {
        "config_id": "config_id",
        "confirm_time": "confirm_time",
        "create_time": "create_time",
        "cs_id": "cs_id",
        "extra": {},
        "image_version_id": "cs_id",
        "name": "name",
        "remark": "备注",
        "ticket_id": "ticket_id",
        "ticket_status": "1",
        "ticket_type": "1",
        "update_time": "create_time",
        "upgrade_strategy": "1"
      }
    ],
    "total": "1"
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
