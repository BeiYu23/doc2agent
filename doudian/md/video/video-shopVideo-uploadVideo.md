# 商家短视频上传

> shopVideo.uploadVideo — 商家短视频上传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家短视频上传 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-uploadVideo` |
| 接口 ID | `doudian.video.shopVideo.uploadVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/uploadVideo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7147 |
| 更新日期 | `2024-12-12` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `url` | body | string | 是 | 视频url，目前支持mp4视频格式 | `https://media.w3.org/2010/05/sintel/trailer.mp4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/uploadVideo?app_key=your_appkey_here&method=shopVideo.uploadVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_id` | string | 任务ID，根据任务ID查询上传任务状态 | `7446661656018420006` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / URL解析失败（sub_code: isv.parameter-invalid:605025001） | 检查URL是否合法，合法例子：https://media.w3.org/2010/05/sintel/trailer.mp4 |
| `20000` | 系统错误（sub_code: isp.service-error:605025003） | 稍后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:605025004） | 稍后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:605025005） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "task_id": "7446661656018420006"
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
  "sub_msg": "URL解析失败"
}
```

## 备注
