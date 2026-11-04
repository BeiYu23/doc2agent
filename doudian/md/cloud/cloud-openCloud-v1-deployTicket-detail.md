# openCloud.v1.deployTicket.detail

> 获取发布详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.v1.deployTicket.detail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/v1/deployTicket/detail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/4148 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cs_id` | body | string | 是 | 容器id | `7239708175753249068` |
| `ticket_id` | body | string | 是 | 发布单id | `7239916236111413548` |
| `volc_account_id` | body | mixed | 否 | 如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100044514` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=openCloud.v1.deployTicket.detail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ticket` | object | 发布单信息 | `` |
| `cs` | object | 容器信息 | `` |
| `image_version` | object | 镜像信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cs": {
      "cluster_name": "测试集群",
      "create_time": "1685628943",
      "cs_env": "1",
      "cs_id": "7239708175753249068",
      "cs_name": "测试服务",
      "cs_resource_status": "60",
      "cs_type": "1",
      "custom_image": {
        "contain_code_package": "false",
        "repo": "\"\"",
        "tag_name": "\"\""
      },
      "image_desc": "java8基础镜像",
      "image_id": "123",
      "image_type": "1",
      "instance_spec": {
        "cron_str": "\"\"",
        "instance_num": "2",
        "limited_cpu": "2",
        "limited_memory": "2000",
        "requested_cpu": "2",
        "requested_memory": "200"
      },
      "update_time": "1685628943"
    },
    "image_version": {
      "create_time": "1685675755",
      "cs_id": "7239708175753249068",
      "cs_name": "测试服务",
      "failed_reason": "\"\"",
      "file_name": "1bc0a0ad0abf4b06abd4161064d99050.jar",
      "remark": "测试",
      "status": "2",
      "version_id": "123",
      "version_name": "v1.4"
    },
    "ticket": {
      "config_id": "7239908695869063468",
      "confirm_time": "1685696102",
      "create_time": "1685696029",
      "cs_id": "7239708175753249068",
      "extra": {},
      "image_version_id": "7239916236111348012",
      "max_surge": "1",
      "max_surge_num": "1",
      "max_unavailable": "0",
      "max_unavailable_num": "0",
      "name": "测试发布",
      "remark": "测试",
      "show_instance_list": "false",
      "ticket_id": "7239916236111413548",
      "ticket_status": "20",
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
