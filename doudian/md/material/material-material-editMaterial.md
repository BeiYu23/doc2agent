# material.editMaterial

> 编辑素材

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.editMaterial` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/editMaterial` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/956 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_id` | body | string | 是 | 素材id | `"7000291764753940780"` |
| `material_name` | body | string | 否 | 素材名称，不得超过50个字符 | `编辑功能.jpg` |
| `to_folder_id` | body | string | 否 | 目标文件夹id，"0"--素材中心 | `"6999833978756661548"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/editMaterial?app_key=your_appkey_here&method=material.editMaterial&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 素材不存在或已被删除（sub_code: isv.business-failed:20001） | 素材不存在或已被彻底删除 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:20001",
  "sub_msg": "素材不存在或已被删除"
}
```

## 备注
