# microapp.UpdateStaticFileMeta

> ISV上传静态资源后绑定相对路径

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.microapp.UpdateStaticFileMeta` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/microapp/UpdateStaticFileMeta` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/2884 |
| 更新日期 | `2024-12-25` |

## 接口说明

- 文档书: 素材中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_type` | body | mixed | 否 | 存储类型。 1: 素材中心。 3:ImageX | `1` |
| `path` | body | string | 是 | 文件相对路径，前端请求获取文件时需填该值 | `/test/path/1.jpg` |
| `material_id` | body | string | 否 | 素材id，由素材中心接口返回 | `1111111111` |
| `file_size` | body | mixed | 否 | 文件大小, 单位为B | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/microapp/UpdateStaticFileMeta?app_key=your_appkey_here&method=microapp.UpdateStaticFileMeta&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数有误（sub_code: isv.parameter-invalid:8000002） | 请参考文档填写正确参数 |
| `40004` | 非法的参数 / appKey参数有误（sub_code: isv.parameter-invalid:8000006） | 请填写正确的 appKey |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:8000001） | 联系开放平台同学解决 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:8000004） | 联系开放平台同学解决 |
| `50002` | 业务处理失败 / 静态资源path字段有重复值，请检查（sub_code: isv.business-failed:9900007） | 使用新的path |

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
  "sub_code": "isv.parameter-invalid:8000002",
  "sub_msg": "参数有误"
}
```

## 备注
