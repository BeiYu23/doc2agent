# material.recoverFolder

> 从回收站恢复文件夹

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.recoverFolder` |
| 中文名 | 从回收站恢复文件夹 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/recoverFolder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1096 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_ids` | body | array | 否 | 需要恢复的文件夹的id列表，不能操作系统文件夹（0：根目录 -1：回收站）。批量操作每次最多20个。 | `["7000254886243746092", "7000254886243746093"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/recoverFolder?app_key=your_appkey_here&method=material.recoverFolder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_ids` | array | 操作成功的文件夹列表 | `["7000254886243746092", "7000254886243746093"]` |
| `failed_map` | string | 操作失败的文件夹及失败的详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_ids": "[\"7000254886243746092\", \"7000254886243746093\"]"
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
