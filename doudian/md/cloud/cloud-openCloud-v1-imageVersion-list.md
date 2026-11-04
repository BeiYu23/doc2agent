# openCloud.v1.imageVersion.list

> 查询镜像列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.v1.imageVersion.list` |
| 中文名 | 查询镜像列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/v1/imageVersion/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/4156 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cs_id` | body | string | 否 | 容器服务id | `7241847582434591010` |
| `start_time` | body | mixed | 否 | 镜像创建的开始时间 | `1687165378` |
| `end_time` | body | mixed | 否 | 镜像创建的开始时间 | `1687165378` |
| `status` | body | mixed | 否 | 构建状态 1:构建中，2：构建成功；3：构建异常 | `2` |
| `volc_account_id` | body | mixed | 否 | 如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100044514` |
| `page_index` | body | mixed | 是 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每页数量，最大100个 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=openCloud.v1.imageVersion.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `image_versions` | array | 镜像列表 | `` |
| `total` | mixed | 镜像总数 | `20` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "image_versions": [
      {
        "create_time": "1685675755",
        "cs_id": "7239708175753249068",
        "cs_name": "ykzhu20230601",
        "failed_reason": "\"\"",
        "file_name": "1bc0a0ad0abf4b06abd4161064d99050.jar",
        "remark": "测试",
        "status": "2",
        "version_id": "7239916236111348012",
        "version_name": "v1.4"
      }
    ],
    "total": "20"
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
