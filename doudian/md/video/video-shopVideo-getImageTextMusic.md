# shopVideo.getImageTextMusic

> 获取图文音乐列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.getImageTextMusic` |
| 中文名 | 获取图文音乐列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/getImageTextMusic` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8140 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query` | body | string | 否 | 歌曲，歌手名称 | `Dance` |
| `page` | body | mixed | 否 | 当前页，从1开始 | `1` |
| `page_size` | body | mixed | 否 | 一次多少条音乐 | `10` |
| `need_recommend` | body | boolean | 否 | 是否需要推荐音乐，默认false | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/getImageTextMusic?app_key=your_appkey_here&method=shopVideo.getImageTextMusic&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `music_list` | array | 音乐列表 | `` |
| `total` | mixed | 总条数 | `10` |
| `recommend_music_list` | array | 推荐音乐列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "music_list": [
      {
        "author": "Richard",
        "clip_id": "6748245563931753523",
        "cover_img": "https://xxx",
        "duration": "65000",
        "music_name": "Bass Dance",
        "music_url": "https://xxx"
      }
    ],
    "recommend_music_list": [
      {
        "author": "Richard",
        "clip_id": "6748245563931753523",
        "cover_img": "https://xxx",
        "duration": "65000",
        "music_name": "Bass Dance",
        "music_url": "https://xxx"
      }
    ],
    "total": "10"
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
