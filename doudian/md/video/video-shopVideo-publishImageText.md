# shopVideo.publishImageText

> 发布图文接口，支持渠道号

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.publishImageText` |
| 中文名 | 发布图文接口，支持渠道号 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/publishImageText` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8139 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `anchor_info` | body | object | 否 | 锚点信息 | `` |
| `  └ anchors` | body | array | 否 | 锚点列表，当前多锚点传递仅支持【挂车+看后搜】 | `` |
| `    └ product_ids` | body | array | 否 | 电商锚点商品id | `11111` |
| `    └ after_search_words` | body | array | 否 | 看后搜小蓝词，必须传3个词，提报词之间用英文逗号分割，每个词最长14字符 | `针织衫怎么穿` |
| `    └ content` | body | string | 否 | 预留字段：锚点文案 | `爆款针织衫` |
| `    └ keyword` | body | string | 否 | 锚点标题，例如小黄车的标题 | `测试标题` |
| `    └ type` | body | string | 否 | 锚点类型，小黄车-3，看后搜-90 | `3` |
| `    └ products` | body | array | 否 | 看后搜承接商品需要设置商品ID+商品名称 | `` |
| `      └ product_name` | body | string | 否 | 商品名称 | `测试商品名称` |
| `      └ is_main_recommend` | body | boolean | 否 | 是否主推品，看后搜必须设置一个主推品 | `true` |
| `      └ product_id` | body | string | 否 | 商品id | `1111111` |
| `related_info` | body | object | 否 | 关联话题信息 | `` |
| `  └ topics` | body | array | 否 | 话题信息 | `` |
| `    └ topic_id` | body | string | 否 | 话题id | `1111` |
| `    └ topic_name` | body | string | 否 | 活动名称 | `测试活动111` |
| `  └ hot_sentence` | body | string | 否 | 热点词 | `热点词111` |
| `publish_info` | body | object | 否 | 发布信息 | `` |
| `  └ schedule_publish_time` | body | number | 否 | 定时发布时间 | `1772701966` |
| `  └ user_id` | body | string | 否 | 用户id，不传则为人店一体账号 | `12121212` |
| `image_info` | body | object | 是 | 图文信息 | `` |
| `  └ audio_info` | body | object | 是 | 音乐信息 | `` |
| `    └ segment_end_time` | body | number | 否 | 结束时间，毫秒 | `120000` |
| `    └ volume` | body | number | 否 | 音量 | `12` |
| `    └ segment_start_time` | body | number | 否 | 开始时间，毫秒 | `10000` |
| `    └ clip_id` | body | string | 是 | 音乐id | `1212121212` |
| `  └ text` | body | string | 是 | 图文正文文案 | `正文文案` |
| `  └ title` | body | string | 是 | 标题 | `标题` |
| `  └ image_url_list` | body | array | 是 | 图片url列表，需先上传到素材中心https://op.jinritemai.com/docs/guide-docs/171/1719 | `https://xxx` |
| `  └ cover_url` | body | string | 否 | 封面图 | `https://xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 发布结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 图文发布失败（sub_code: isv.business-failed:60488027） | 图文发布失败 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:60488027",
  "sub_msg": "图文发布失败"
}
```

## 备注
