# 彻底删除文件夹

> material.deleteFolder — 彻底删除文件夹，包括当前文件夹和当前文件夹包含的所有子文件夹和素材。删除后不可查询。
批量操作时，要求入参中的所有文件夹在同一个父文件夹下。

| 元信息 | 值 |
| --- | --- |
| 中文名 | 彻底删除文件夹 |
| 文档地址 | `/docs/doudian/material/material-material-deleteFolder` |
| 接口 ID | `doudian.material.material.deleteFolder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/deleteFolder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1139 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V3.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_ids` | body | array | 否 | 文件夹id list，最多不超过20个 | `["7001012973925941548"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/deleteFolder?app_key=your_appkey_here&method=material.deleteFolder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_ids` | array | 操作成功的文件夹id列表 | `["7001012973925941548"]` |
| `failed_map` | string | 操作失败的的文件夹及错误详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 系统文件夹，不可操作（sub_code: isv.parameter-invalid:20001） | 参数错误 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_ids": "[\"7001012973925941548\"]"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "系统文件夹，不可操作"
}
```

## 备注
