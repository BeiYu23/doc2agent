# 记录秒级数据追踪数据

> second.ecomInsight.trackSecondVideoId — 记录秒级数据追踪数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 记录秒级数据追踪数据 |
| 文档地址 | `/docs/doudian/video/video-second-ecomInsight-trackSecondVideoId` |
| 接口 ID | `doudian.video.second.ecomInsight.trackSecondVideoId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8634 |
| 更新日期 | `2026-10-10` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `second_track_video_id` | body | string | 否 | 秒级追踪视频ID | `video_987654` |
| `task_id` | body | mixed | 否 | 任务ID | `123456789` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.trackSecondVideoId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据对象 | `` |
| `msg` | string | 全局提示信息 | `请求成功` |
| `code` | mixed | 返回码 | `200` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "200",
    "data": {
      "id": "1001",
      "msg": "操作成功",
      "success": "true"
    },
    "msg": "请求成功"
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
