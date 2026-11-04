# 创建镜像

> openCloud.v1.imageVersion.create — 创建镜像

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建镜像 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-v1-imageVersion-create` |
| 接口 ID | `doudian.cloud.openCloud.v1.imageVersion.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/v1/imageVersion/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/4155 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cs_id` | body | string | 是 | 容器服务id | `7239708175753249068` |
| `version_name` | body | string | 是 | 版本名称 | `v1.0` |
| `remark` | body | string | 是 | 备注 | `测试` |
| `file_uri` | body | string | 是 | 程序包上传素材中心后返回的uri | `http://p-ecom-open-boe-sign.bytedance.net/tos-boe-i-39cvtodz2w/1bc0a0ad0abf4b06abd4161064d99050.jar?x-orig-authkey=ak39cvtodz2w&x-orig-expires=1685623279&x-orig-sign=DXC0yu4DmMiQFRPKzsbhMP%2B1sLI%3D` |
| `file_name` | body | string | 是 | 文件名称 | `demo.jar` |
| `cs_name` | body | string | 是 | 容器名称 | `mar-pod` |
| `volc_account_id` | body | mixed | 否 | 如果是强管控、跨境、微应用等租户，需要传火山账号id | `2100384108` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=openCloud.v1.imageVersion.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `version_id` | string | 镜像版本id | `7241903236771234092` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "version_id": "7241903236771234092"
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
