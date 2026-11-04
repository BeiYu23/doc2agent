# shopVideo.publishVideoNew

> 发布视频新接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.publishVideoNew` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/publishVideoNew` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7489 |
| 更新日期 | `2025-10-16` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `publish_info` | body | object | 是 | 发布信息 | `` |
| `  └ source` | body | mixed | 是 | 来自open端默认传3 | `3` |
| `  └ user_id` | body | string | 否 | 用户id，不传则为人店一体账号 | `111` |
| `  └ schedule_publish_time` | body | mixed | 否 | 定时发布时间 | `112121212` |
| `video_info` | body | object | 是 | 视频信息 | `` |
| `  └ desc` | body | string | 是 | 视频描述 | `这是视频描述` |
| `  └ cover_image_uri` | body | string | 否 | 封面地址。 | `12122121` |
| `  └ media_id` | body | string | 是 | 视频id，格式如：v0d27cg10001csve2qfog65o283c1h0g | `112121` |
| `  └ title` | body | string | 是 | 视频标题 | `这是视频标题` |
| `anchor_info` | body | object | 否 | 锚点信息 | `` |
| `  └ anchors` | body | array | 否 | 锚点列表 | `` |
| `    └ keyword` | body | string | 否 | 锚点标题，例如小黄车的标题 | `锚点标题` |
| `    └ product_ids` | body | array | 否 | 商品id，挂车和非挂车均需要 | `121212122` |
| `    └ anchor_draft_id` | body | string | 否 | 锚点草稿id。发布挂车视频时必传 | `121212122` |
| `    └ content` | body | string | 否 | 锚点文案 | `锚点文案` |
| `    └ type` | body | mixed | 否 | 锚点类型，3-挂车，7-非挂车 | `3` |
| `related_info` | body | object | 否 | 相关信息 | `` |
| `  └ topics` | body | array | 否 | 话题信息 | `` |
| `    └ topic_name` | body | string | 否 | 活动名称 | `这是活动名称` |
| `    └ topic_id` | body | string | 否 | 话题id | `121211212` |
| `  └ hot_sentence` | body | string | 否 | 热点词 | `热点词` |
| `app_info` | body | object | 是 | 应用信息 | `` |
| `  └ app_id` | body | mixed | 是 | app_key | `appid` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/publishVideoNew?app_key=your_appkey_here&method=shopVideo.publishVideoNew&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应参数 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 1000001:定时发布时间不能大于当前时间+14天（sub_code: isv.parameter-invalid:1000001） | 定时发布时间不能大于当前时间+14天 |
| `50002` | 业务处理失败 / 60488027:视频发布失败（sub_code: isv.business-failed:60488027） | 视频发布失败 |
| `50002` | 业务处理失败 / 60488028:视频投稿功能已封禁（sub_code: isv.business-failed:60488028） | 视频投稿功能已封禁 |
| `50002` | 业务处理失败 / 60488029:抱歉，今天投稿次数已达到上限，请明天再试（sub_code: isv.business-failed:60488029） | 抱歉，今天投稿次数已达到上限，请明天再试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "item_id": "1212121212"
    }
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
  "sub_code": "isv.parameter-invalid:1000001",
  "sub_msg": "1000001:定时发布时间不能大于当前时间+14天"
}
```

## 备注
