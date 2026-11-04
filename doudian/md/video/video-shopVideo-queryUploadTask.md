# 查询url上传视频接口的任务信息（状态

> shopVideo.queryUploadTask — 查询url上传视频接口的任务信息（状态、上传成功的视频id等）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询url上传视频接口的任务信息（状态 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-queryUploadTask` |
| 接口 ID | `doudian.video.shopVideo.queryUploadTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/queryUploadTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7151 |
| 更新日期 | `2024-12-12` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | string | 是 | uploadVideo接口得到的task_id | `7447060952975049010` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/queryUploadTask?app_key=your_appkey_here&method=shopVideo.queryUploadTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `vid` | string | media_id，v开头的字符串 | `v0d27cg10001cqclamfog40zzm86o6v0` |
| `status` | mixed | 短视频上传状态，0=初始化，1=上传中，2=上传成功，3=上传失败 | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / task_id不正确（sub_code: isv.parameter-invalid:605025001） | 确认task_id是否有误 |
| `20000` | 系统错误 / 数据库查询失败（sub_code: isp.service-error:605025006） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "status": "2",
    "vid": "v0d27cg10001cqclamfog40zzm86o6v0"
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
  "sub_msg": "task_id不正确"
}
```

## 备注
