# material.editFolder

> 编辑/移动文件夹

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.editFolder` |
| 中文名 | 编辑/移动文件夹 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/editFolder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/948 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id` | body | string | 是 | 文件夹id，不能操作系统文件夹（0：根目录 -1：回收站） | `"70029608590225411001510"` |
| `name` | body | string | 否 | 新的文件夹名称 | `我是新的文件夹名称` |
| `to_folder_id` | body | string | 否 | 需要移动到的父文件夹id | `"70029608590225411001510"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/editFolder?app_key=your_appkey_here&method=material.editFolder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 文件夹ID错误，请输入正确的文件夹ID（sub_code: isv.parameter-invalid:20001） | 文件夹id不存，检查参数 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "文件夹ID错误，请输入正确的文件夹ID"
}
```

## 备注
