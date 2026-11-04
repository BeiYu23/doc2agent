# 创建发布单

> openCloud.v1.deployTicket.create — 创建发布单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建发布单 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-v1-deployTicket-create` |
| 接口 ID | `doudian.cloud.openCloud.v1.deployTicket.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/v1/deployTicket/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/4149 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `config_id` | body | string | 是 | 配置id | `7239908695869063468` |
| `cs_id` | body | string | 是 | 容器服务id | `7239708175753249068` |
| `image_version_id` | body | string | 是 | 镜像版本id | `7239916236111348012` |
| `remark` | body | string | 否 | 备注 | `测试` |
| `upgrade_strategy` | body | mixed | 否 | 实例更新策略。1:滚动更新；2:重新创建 | `1` |
| `max_unavailable` | body | mixed | 否 | 最大不可用，百分比，范围[0-100] | `1` |
| `max_surge` | body | mixed | 否 | 最大超量，百分比，范围[0-100] | `3` |
| `cron_job_advanced_conf` | body | object | 否 | 高级配置 | `` |
| `  └ successful_jobs_history_limit` | body | mixed | 否 | 成功任务保留数, 取值: "空,[0,65535]", 默认 空 | `0` |
| `  └ failed_jobs_history_limit` | body | mixed | 否 | 失败任务保留数, 取值: "空,[0,65535]", 默认 空 | `0` |
| `  └ concurrency_policy` | body | mixed | 是 | 并发策略, 默认 Allow。 0:允许, 默认；1：禁止；2:替换 | `0` |
| `  └ completions` | body | mixed | 否 | 成功运行次数, 取值: "空,[0,65535]", 默认 空 | `0` |
| `  └ parallelism` | body | mixed | 否 | 可并行数, 取值: "空,[0,65535]", 默认 空 | `0` |
| `  └ active_deadline_seconds` | body | mixed | 否 | 最大超时时间, 取值: "空,[0,65535]" 默认 空, 单位: 秒 | `0` |
| `  └ backoff_limit` | body | mixed | 否 | 重试次数, 取值: "空,[0,65535]", 默认 空 | `0` |
| `  └ restart_policy` | body | mixed | 是 | 重启策略。0:永不重启；1：失败时重启 | `0` |
| `volc_account_id` | body | mixed | 否 | 如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100044514` |
| `custom_Image` | body | object | 否 | 自定义镜像版本，仅自带程序包的自定义镜像发布需传该参数 | `` |
| `  └ repo` | body | string | 否 | 自定义镜像名称 | `test-image` |
| `  └ tag_name` | body | string | 否 | 镜像版本 | `1.0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=openCloud.v1.deployTicket.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ticket` | object | 发布单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ticket": {
      "config_id": "7239908695869063468",
      "confirm_time": "-2006054656",
      "create_time": "1685696029",
      "cs_id": "7239708175753249068",
      "extra": {},
      "image_version_id": "7239916236111348012",
      "max_surge": "1",
      "max_surge_num": "1",
      "max_unavailable": "0",
      "max_unavailable_num": "0",
      "name": "测试",
      "remark": "test",
      "show_instance_list": "false",
      "ticket_id": "7239916236111413548",
      "ticket_status": "10",
      "ticket_type": "0",
      "update_time": "1685696029",
      "upgrade_strategy": "1",
      "use_time": "0"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
