# openCloud.containerService.create

> 创建容器服务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.containerService.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/containerService/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/7609 |
| 更新日期 | `2025-07-17` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cluster_id` | body | string | 否 | 关联集群id | `"7020346122334567"` |
| `image_desc` | body | string | 否 | 镜像描述 | `"java8基础镜像"` |
| `deploy_path` | body | string | 否 | 部署路径 | `/data/work/{container_service_name}` |
| `cs_env` | body | mixed | 否 | 环境信息 | `2` |
| `volc_account_id` | body | mixed | 否 | 火山账号，如果使用强管控租户，需要传对应火山id | `2100000000` |
| `cluster_name` | body | string | 否 | 关联集群名称 | `"auto-test-cluster"` |
| `log_path` | body | string | 否 | 日志收集路径(日志服务只收集该路径下的日志) | `/data/work/{container_service_name}/logs` |
| `cs_name` | body | string | 否 | 容器服务名称 | `container_service_name` |
| `instance_spec` | body | object | 否 | 实例配置 | `` |
| `  └ requested_cpu` | body | string | 否 | CPU请求 单位:核 | `1` |
| `  └ requested_memory` | body | string | 否 | 内存请求 单位:MiB | `200` |
| `  └ limited_cpu` | body | string | 否 | CPU上限 单位:核 | `1` |
| `  └ limited_memory` | body | string | 否 | 内存上限 单位:MiB | `220` |
| `  └ instance_num` | body | mixed | 否 | 实例个数i32 | `1` |
| `  └ cron_str` | body | string | 否 | cron 表达式 | `"cron_str"` |
| `cs_type` | body | mixed | 否 | 容器服务类型 | `1` |
| `deploy_type` | body | mixed | 否 | 部署方式 | `1` |
| `desc` | body | string | 否 | 描述 | `"desc"` |
| `image_id` | body | string | 否 | 镜像Id | `"image_id"` |
| `image_type` | body | mixed | 否 | 镜像类型 | `1` |
| `custom_image` | body | object | 否 | 自定义镜像 | `` |
| `  └ repo` | body | string | 否 | 镜像名称 | `"repo"` |
| `  └ tag_name` | body | string | 否 | 镜像版本 | `"v1"` |
| `  └ contain_code_package` | body | boolean | 否 | 镜像是否包含代码包 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/containerService/create?app_key=your_appkey_here&method=openCloud.containerService.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cs_id` | string | 容器服务id | `"cs-id"` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cs_id": "\"cs-id\""
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
