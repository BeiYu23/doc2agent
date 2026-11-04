# shopVideo.genUploadAuth

> 获取SDK上传视频的授权

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.genUploadAuth` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/genUploadAuth` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7150 |
| 更新日期 | `2024-12-12` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `upload_scene` | body | mixed | 是 | 上传场景：1-短视频发稿 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/genUploadAuth?app_key=your_appkey_here&method=shopVideo.genUploadAuth&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `current_time` | string | 生成授权时间 | `2024-12-11T16:15:34+08:00` |
| `access_key_id` | string | 临时的accessKeyId | `YOUR_ACCESS_KEY_ID` |
| `secret_access_key` | string | 临时的secretAccessKey | `YOUR_SECRET_KEY` |
| `session_token` | string | 临时的会话token | `STS2eyJMVEFjY2Vzc0tleUlEIjoiQUtMVE9USTBOamd5TTJJeE5XTTROR0l3WTJGalpESmxaV1F6T0RrMU56SmhOVGMiLCJBY2Nlc3NLZXlJRCI6IkFLVFBPVFZtWkRObU1USTJOemMyTkRsaFpHRmxOekF6TW1WaFlqaGtNbVpsWkdJIiwiU2lnbmVkU2VjcmV0QWNjZXNzS2V5IjoiSXgwaS9INHVhL3cxL2lWb2dic1cwNDZKQTZJTURQQTl6UlpOTGhjR2RRUkF5Uy80MlF6UFR5UXlQZDlxc2FVT1dwM1ZzSCs4ZVMrMjhHTDk4d3VEUi9oSjRUaVcwZFYxSzFSaCtWY09LbVU9IiwiRXhwaXJlZFRpbWUiOjE3MzM5MDU1MzQsIlBvbGljeVN0cmluZyI6IntcIlN0YXRlbWVudFwiOlt7XCJFZmZlY3RcIjpcIkFsbG93XCIsXCJBY3Rpb25cIjpbXCJ2b2Q6QXBwbHlVcGxvYWRcIixcInZvZDpBcHBseVVwbG9hZElubmVyXCIsXCJ2b2Q6Q29tbWl0VXBsb2FkXCIsXCJ2b2Q6Q29tbWl0VXBsb2FkSW5uZXJcIixcInZvZDpHZXRVcGxvYWRDYW5kaWRhdGVzXCIsXCJJbWFnZVg6QXBwbHlJbWFnZVVwbG9hZFwiLFwiSW1hZ2VYOkNvbW1pdEltYWdlVXBsb2FkXCIsXCJJbWFnZVg6QXBwbHlVcGxvYWRJbWFnZUZpbGVcIixcIkltYWdlWDpDb21taXRVcGxvYWRJbWFnZUZpbGVcIl0sXCJSZXNvdXJjZVwiOltcIipcIl0sXCJDb25kaXRpb25cIjpcIntcXFwiUFNNXFxcIjpcXFwiY21wLmVjb20ub3Blbl9hYmlsaXR5XFxcIixcXFwiVXNlcklkXFxcIjpcXFwiNzQyNDQ1MjA3NTU0OTI5NjE2NlxcXCJ9XCJ9XX0iLCJTaWduYXR1cmUiOiJjYzc2MWJmNmQzNGY3MTM1OTU4OThmZjIwYTI4YmRlNWY5MGYxMzI0OGM1MDM2YjRlZDFhMTFlOWY5ZWQ4MTFkIn0=` |
| `space_name` | string | 空间名，上传时必须使用该空间，否则会上传失败 | `ecom-shop-material` |
| `expired_time` | string | 授权过期时间 | `2024-12-11T16:25:34+08:00` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:605025001） | 根据提示文案修改参数 |
| `20000` | 系统错误 / 生成授权失败（sub_code: isp.service-error:605025002） | 正常情况不会出现，可尝试重试 |

## 响应示例

成功：

```json
{
  "data": {
    "access_key_id": "YOUR_ACCESS_KEY_ID",
    "current_time": "2024-12-11T16:15:34+08:00",
    "expired_time": "2024-12-11T16:25:34+08:00",
    "secret_access_key": "YOUR_SECRET_KEY",
    "session_token": "STS2eyJMVEFjY2Vzc0tleUlEIjoiQUtMVE9USTBOamd5TTJJeE5XTTROR0l3WTJGalpESmxaV1F6T0RrMU56SmhOVGMiLCJBY2Nlc3NLZXlJRCI6IkFLVFBPVFZtWkRObU1USTJOemMyTkRsaFpHRmxOekF6TW1WaFlqaGtNbVpsWkdJIiwiU2lnbmVkU2VjcmV0QWNjZXNzS2V5IjoiSXgwaS9INHVhL3cxL2lWb2dic1cwNDZKQTZJTURQQTl6UlpOTGhjR2RRUkF5Uy80MlF6UFR5UXlQZDlxc2FVT1dwM1ZzSCs4ZVMrMjhHTDk4d3VEUi9oSjRUaVcwZFYxSzFSaCtWY09LbVU9IiwiRXhwaXJlZFRpbWUiOjE3MzM5MDU1MzQsIlBvbGljeVN0cmluZyI6IntcIlN0YXRlbWVudFwiOlt7XCJFZmZlY3RcIjpcIkFsbG93XCIsXCJBY3Rpb25cIjpbXCJ2b2Q6QXBwbHlVcGxvYWRcIixcInZvZDpBcHBseVVwbG9hZElubmVyXCIsXCJ2b2Q6Q29tbWl0VXBsb2FkXCIsXCJ2b2Q6Q29tbWl0VXBsb2FkSW5uZXJcIixcInZvZDpHZXRVcGxvYWRDYW5kaWRhdGVzXCIsXCJJbWFnZVg6QXBwbHlJbWFnZVVwbG9hZFwiLFwiSW1hZ2VYOkNvbW1pdEltYWdlVXBsb2FkXCIsXCJJbWFnZVg6QXBwbHlVcGxvYWRJbWFnZUZpbGVcIixcIkltYWdlWDpDb21taXRVcGxvYWRJbWFnZUZpbGVcIl0sXCJSZXNvdXJjZVwiOltcIipcIl0sXCJDb25kaXRpb25cIjpcIntcXFwiUFNNXFxcIjpcXFwiY21wLmVjb20ub3Blbl9hYmlsaXR5XFxcIixcXFwiVXNlcklkXFxcIjpcXFwiNzQyNDQ1MjA3NTU0OTI5NjE2NlxcXCJ9XCJ9XX0iLCJTaWduYXR1cmUiOiJjYzc2MWJmNmQzNGY3MTM1OTU4OThmZjIwYTI4YmRlNWY5MGYxMzI0OGM1MDM2YjRlZDFhMTFlOWY5ZWQ4MTFkIn0=",
    "space_name": "ecom-shop-material"
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
  "sub_code": "isv.parameter-invalid:605025001",
  "sub_msg": "参数错误"
}
```

## 备注
