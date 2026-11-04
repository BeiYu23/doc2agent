# pigeon.getVideoPlayUrl

> 获取飞鸽视频播放URL

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.getVideoPlayUrl` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/getVideoPlayUrl` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/5947 |
| 更新日期 | `2023-12-20` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `video_id` | body | string | 是 | 视频ID | `v121ewadadad` |
| `conversation_id` | body | string | 是 | 会话ID | `7314506401752139315` |
| `server_msg_id` | body | string | 是 | 消息ID | `7314259492131127588` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/getVideoPlayUrl?app_key=your_appkey_here&method=pigeon.getVideoPlayUrl&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cover_url` | string | 视频封面图 | `https://` |
| `duration` | string | 视频时长，单位秒 | `602.1` |
| `url_expire` | mixed | URL过期时间 | `86400` |
| `main_play_url` | string | 播放URL | `https://` |
| `backup_play_url` | string | 播放URL，如果main_play_url不可用，可切换到此URL | `https://` |
| `format` | string | 视频格式 | `mp4` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数异常，请填写正确的参数（sub_code: isv.parameter-invalid:605022003） | 请填写正确的参数 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:605022001） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 参数异常，会话信息不存在（sub_code: isv.parameter-invalid:605022002） | 参数异常，会话信息不存在 |
| `40004` | 非法的参数 / 参数异常，消息不存在（sub_code: isv.parameter-invalid:605022006） | 参数异常，消息不存在 |
| `40004` | 非法的参数 / 参数异常，视频消息不存在（sub_code: isv.parameter-invalid:605022007） | 参数异常，视频消息不存在 |

## 响应示例

成功：

```json
{
  "data": {
    "backup_play_url": "https://",
    "cover_url": "https://",
    "duration": "602.1",
    "format": "mp4",
    "main_play_url": "https://",
    "url_expire": "86400"
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
  "sub_code": "isv.parameter-invalid:605022003",
  "sub_msg": "参数异常，请填写正确的参数"
}
```

## 备注
