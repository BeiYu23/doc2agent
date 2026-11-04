# second.ecomInsight.getAigcTaskResult

> 获取任务结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.getAigcTaskResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8353 |
| 更新日期 | `2026-07-23` |

## 接口说明

- 文档书: 短视频API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | mixed | 否 | 主任务id | `123` |
| `id` | body | mixed | 否 | 子任务id | `1` |
| `task_type` | body | string | 否 | 任务类型： VideoRecommending、VideoSearch、VideoUnderstand | `VideoRecommending` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.getAigcTaskResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `video_recommending` | object | 视频推荐结果 | `` |
| `video_search` | object | 视频搜索 | `` |
| `video_understand` | object | 视频理解 | `` |
| `msg` | string | 消息 | `xxxx` |
| `code` | mixed | 状态码 | `0` |
| `video_search_top_short` | object | 短视频top榜单数据 | `` |

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
    "msg": "xxxx",
    "video_recommending": {
      "msg": "xxxx",
      "page": "1",
      "page_size": "20",
      "status": "3",
      "task_id": "123",
      "total": "123",
      "video_list": [
        {
          "product_id": "xxxxx",
          "product_name": "xxxxx",
          "video_id": "123123",
          "video_title": "xxxx",
          "video_url": "xxxxx"
        }
      ]
    },
    "video_search": {
      "msg": "xxxx",
      "page": "1",
      "page_size": "20",
      "status": "3",
      "task_id": "123",
      "total": "12313",
      "video_list": [
        {
          "product_id": "12313",
          "product_name": "xxxxxx",
          "video_id": "123123",
          "video_title": "xxxxxx",
          "video_url": "xxxxxx"
        }
      ]
    },
    "video_search_top_short": {
      "code": "0",
      "data": {
        "page": "xxxx",
        "page_size": "30",
        "records": [
          {
            "asr": "xxxx",
            "avatar_uri": "xxxx",
            "aweme_id": "xxxxx",
            "comment_cnt_all": "xxx",
            "ecom_prod_buy_pv_7d": "xxxx",
            "ecom_prod_click_pv_7d": "xxxx",
            "ecom_prod_gmv_7d": "xxxx",
            "ecom_prod_show_click_ratio_7d": "xxxx",
            "favourite_cnt_all": "xxxx",
            "finish_vv_pv_7d": "xxxx",
            "fives_finish_vv_ratio_7d": "xxxx",
            "follow_uv": "xxxx",
            "id": "xxx",
            "item_duration": "xxxxx",
            "like_cnt_all": "xxxx",
            "nickname": "xxxxx",
            "ocr": "xxxx",
            "product_first_cat_name": "xxxx",
            "product_leaf_cat_name": "xx",
            "product_name": "xxxx",
            "product_second_cat_name": "xxxx",
            "share_cnt_all": "xxxx",
            "shop_name": "xxxxx",
            "video_create_date": "xxxx",
            "video_first_tag_name": "xxxxx",
            "video_id": "xxx",
            "video_second_tag_name": "xxxx",
            "video_third_tag_name": "xxxx",
            "video_title": "xxxx",
            "video_url": "xxxx",
            "vv_pv_7d": "xxxx"
          }
        ],
        "task_id": "123",
        "total": "xxx"
      },
      "msg": "xxxx"
    },
    "video_understand": {
      "full_voiceover_script": "xxxxx",
      "msg": "xxx",
      "status": "3",
      "storyboard_list": [
        {
          "duration": "3",
          "index": "1",
          "scene_description": "xxxxx",
          "screenshot_url": "xxxxx",
          "voiceover_text": "xxxx"
        }
      ],
      "task_id": "2"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
