# second.ecomInsight.querySecondVideoData

> 获取秒级追踪数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.querySecondVideoData` |
| 中文名 | 获取秒级追踪数据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8633 |
| 更新日期 | `2026-09-18` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `second_track_video_ids` | body | array | 否 | 需追踪秒级数据视频id列表 | `["123123"]` |
| `start_date` | body | string | 否 | 开始日期 | `2026-09-04` |
| `end_date` | body | string | 否 | 结束日期 | `2026-09-04` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.querySecondVideoData&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 全局返回码，0表示成功，非0表示失败 | `0` |
| `data` | object | 返回的业务数据主体 | `` |
| `msg` | string | 全局返回信息描述 | `请求成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "msg": "成功",
      "records": [
        {
          "click_cnt": "[0.0,0.2,0.4,0.0]",
          "comment_cnt": "[0.0,0.2,0.4,0.0]",
          "interact_cnt": "[0.0,0.2,0.4,0.0]",
          "like_cnt": "[0.0,0.2,0.4,0.0]",
          "loss_cnt": "[0.0,0.2,0.4,0.0]",
          "video_duration": "120.5",
          "video_id": "789012"
        }
      ],
      "status": "0"
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
