# 查询service列表

> openCloud.backendService.list — 查询service列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询service列表 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-backendService-list` |
| 接口 ID | `doudian.cloud.openCloud.backendService.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/backendService/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/7608 |
| 更新日期 | `2025-07-17` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `volc_account_id` | body | mixed | 是 | 火山账号ID。如果是强管控、跨境、微应用等租户，需要传火山账号id | `210000000` |
| `cluster_id` | body | string | 是 | 容器服务ID | `7020346200001000101` |
| `bs_types` | body | string | 是 | 后端服务 | `"bs_types"` |
| `bs_type` | body | mixed | 是 | 服务类型 | `1` |
| `paging` | body | mixed | 是 | 分页 | `2` |
| `page_index` | body | mixed | 是 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每页数量，最大100 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/backendService/list?app_key=your_appkey_here&method=openCloud.backendService.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `service_list` | array | 服务列表 | `` |
| `total` | mixed | 服务总数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "service_list": [
      {
        "access_ip": "\"ip\"",
        "create_time": "1712160000000",
        "ports": [
          {
            "cs_port": "\"\"",
            "name": "\"name\"",
            "node_port": "1",
            "protocol": "\"protocol\"",
            "service_port": "\"service_port\""
          }
        ],
        "service_name": "\"service_name\"",
        "service_type": "1",
        "update_time": "1712160000000"
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
