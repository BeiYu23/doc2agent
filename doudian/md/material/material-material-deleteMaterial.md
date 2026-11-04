# material.deleteMaterial

> 彻底删除素材

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.deleteMaterial` |
| 中文名 | 彻底删除素材 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/deleteMaterial` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1138 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_ids` | body | array | 是 | 要删除的素材id列表，最大不得超过100个，只支持删除同一级目录下的素材 | `["123"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/deleteMaterial?app_key=your_appkey_here&method=material.deleteMaterial&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_ids` | array | 操作成功的素材id | `["123"]` |
| `failed_map` | string | 操作失败的素材id和原因 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 素材ID无效或状态错误（sub_code: isv.parameter-invalid:20001） | 素材不存在，原因有：已被删除或主从延迟导致素材不存在 |
| `40004` | 非法的参数 / 数据可能已被修改，请刷新后重新提交（sub_code: isv.parameter-invalid:22004） | 有并发请求，修改参数重新请求 |
| `40004` | 非法的参数 / 请求已生效，请勿重复请求（sub_code: isv.parameter-invalid:31001） | 并发请求，不要重试 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_ids": "[\"123\"]"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10004",
  "sub_msg": "系统异常，请稍后重试"
}
```

## 备注
