# 查询容器服务

> openCloud.containerService.detail — 查询容器服务详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询容器服务 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-containerService-detail` |
| 接口 ID | `doudian.cloud.openCloud.containerService.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/containerService/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/6451 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cs_id` | body | string | 是 | 容器服务ID | `7345699782717079843` |
| `volc_account_id` | body | mixed | 否 | 火山账号ID。如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100003854` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/containerService/detail?app_key=your_appkey_here&method=openCloud.containerService.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cs_detail` | object | 容器服务详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cs_detail": {
      "cluster_id": "7034062930271863071",
      "cluster_name": "test-cluster",
      "create_time": "2024-04-17T07:11:01Z",
      "cs_env": "1",
      "cs_id": "7172913559133995301",
      "cs_name": "javademo",
      "cs_resource_status": "0",
      "cs_type": "1",
      "custom_image": {
        "contain_code_package": "true",
        "repo": "javademo",
        "tag_name": "V1.0"
      },
      "deploy_path": "/data/work/javademo",
      "desc": "测试容器服务",
      "hpa_metrics": {
        "cpu_metrics": "80",
        "max_replicas": "10",
        "memory_metrics": "80",
        "min_replicas": "1"
      },
      "image_desc": "测试程序包",
      "image_id": "7302247702547415334",
      "image_type": "2",
      "instance_list": [
        {
          "create_time": "2024-04-17T07:11:02Z",
          "error_reason": "失败原因",
          "instance_name": "javademo-654c99b654-6kfc5",
          "node_ip": "172.16.0.170",
          "pod_ip": "192.168.96.218",
          "restart_times": "0",
          "running_status": "Running",
          "running_time": "1"
        }
      ],
      "instance_spec": {
        "cron_str": "*/1 * * * *",
        "instance_num": "1",
        "limited_cpu": "2",
        "limited_memory": "2048",
        "requested_cpu": "1",
        "requested_memory": "1024"
      },
      "job_list": [
        {
          "active": "0",
          "complete_time": "2024-04-17T07:11:01Z",
          "create_time": "2024-04-17T07:11:01Z",
          "failed": "0",
          "name": "auto-test-cron3-20230901-1713337860",
          "namespace": "opcloudns111558443992",
          "succeeded": "1",
          "vke_cluster_id": "cc6f05tersfeikvsbsur0"
        }
      ],
      "log_path": "/data/work/javademo/logs",
      "open_app_id": "7265156274944312888",
      "open_app_name": "抖店云测试应用",
      "update_time": "2024-04-17T07:11:01Z"
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
