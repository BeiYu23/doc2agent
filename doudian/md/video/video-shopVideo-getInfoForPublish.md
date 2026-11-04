# 查询投稿需要的信息

> shopVideo.getInfoForPublish — 查询投稿需要的信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询投稿需要的信息 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-getInfoForPublish` |
| 接口 ID | `doudian.video.shopVideo.getInfoForPublish` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/getInfoForPublish` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7148 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `need_hotspot` | body | boolean | 是 | 是否需要热点数据 | `true` |
| `need_activity` | body | boolean | 是 | 是否查询创作者活动 | `true` |
| `need_alliance_limit` | body | boolean | 是 | 是否需要检查挂车次数限制 | `true` |
| `need_image_alliance_limit` | body | boolean | 否 | 是否需要检查图文挂车次数限制 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/getInfoForPublish?app_key=your_appkey_here&method=shopVideo.getInfoForPublish&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `hotspot_info` | object | 热点信息 | `` |
| `activity_list` | array | 活动列表 | `` |
| `alliance_limit_info` | object | 挂车次数限制信息 | `` |
| `image_alliance_limit_info` | object | 图文挂车次数限制信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 根据提示文案调整参数 |
| `50002` | 业务处理失败 / 店铺未绑定人店一体账号（sub_code: isv.business-failed:628002009） | 引导商家去抖店-内容-短视频创作tab绑定抖音账号 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_list": [
      {
        "activity_id": "7330597710854362122",
        "activity_name": "艺术在抖音",
        "head_image": "https://lf-gaia-dy.douyinstatic.com/obj/gaia-dy/7423651c0d3ed2c206c641564a68adbe.jpg",
        "jump_url": "https://webcast.amemv.YOUR_SECRET_KEY?should_full_screen=1&show_back=0&hide_nav_bar=1&hide_status_bar=1&auto_play_bgm=1&web_bg_color=%23FFbbd8fd&loader_name=forest&disable_all_bounces=1&__live_platform__=webcast&appType=webcast&magic_page_no=1&magic_source=mp_offline"
      }
    ],
    "alliance_limit_info": {
      "can_bind": "true",
      "current_bind_num": "1",
      "remain_bind_num": "1"
    },
    "hotspot_info": {
      "hotspot_list": [
        {
          "name": "花样玩雪的101种方式"
        }
      ]
    },
    "image_alliance_limit_info": {
      "can_bind": "true",
      "current_bind_num": "1",
      "remain_bind_num": "1"
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
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "参数错误"
}
```

## 备注
