# 更新容器服务

> openCloud.containerService.update — 更新容器服务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 更新容器服务 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-containerService-update` |
| 接口 ID | `doudian.cloud.openCloud.containerService.update` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/containerService/update` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/6452 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cs_id` | body | string | 是 | 容器服务ID | `7345699782717079843` |
| `instance_spec` | body | object | 是 | 容器服务规格 | `` |
| `  └ requested_cpu` | body | string | 是 | CPU请求值 | `1` |
| `  └ requested_memory` | body | string | 是 | 内存请求值 | `1024` |
| `  └ limited_cpu` | body | string | 是 | CPU上限值 | `2` |
| `  └ limited_memory` | body | string | 是 | 内存上限值 | `2048` |
| `  └ instance_num` | body | mixed | 是 | 实例个数 | `2` |
| `  └ cron_str` | body | string | 是 | cron表达式，无状态负载类型的容器服务无需传该参数 | `*/1 * * * *` |
| `volc_account_id` | body | mixed | 否 | 火山账号ID。如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100003854` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/containerService/update?app_key=your_appkey_here&method=openCloud.containerService.update&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
