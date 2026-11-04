# second.ecomInsight.queryTrackVideoData

> 查询追踪数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.queryTrackVideoData` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8376 |
| 更新日期 | `2026-09-08` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `track_video_id` | body | array | 否 | 需要查询的video_id，必须是之前数据追踪传入的 | `["1","2","3"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.queryTrackVideoData&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg` | string | 消息 | `xxx` |
| `code` | mixed | 状态码 | `0` |
| `data` | array | 返回的视频数据列表 | `` |

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
    "data": [
      {
        "comment_cnt_7d": "456",
        "comment_cnt_all": "7890",
        "date": "2024-05-20",
        "ecom_prod_addcart_uv_7d": "2345",
        "ecom_prod_buy_uv_7d": "1234",
        "ecom_prod_click_uv_7d": "12345",
        "ecom_prod_gmv_7d": "123456.78",
        "ecom_prod_show_click_ratio_7d": "0.15",
        "ecom_prod_show_uv_7d": "45678",
        "favourite_cnt_7d": "543",
        "favourite_cnt_all": "12345",
        "finish_vv_pv_7d": "5432",
        "finish_vv_ratio_7d": "0.75",
        "five_s_finish_vv_pv_7d": "4321",
        "five_s_finish_vv_ratio_7d": "0.85",
        "is_cart_video": "false",
        "is_qianchuan": "true",
        "is_xingtu": "true",
        "kol_fans_num": "100000",
        "kol_nickname": "美食达人小张",
        "kol_type": "美食达人",
        "like_cnt_7d": "4567",
        "like_cnt_all": "123456",
        "product_first_cate_name": "厨房电器",
        "product_id": "987654",
        "product_leaf_cate_name": "中式炒锅",
        "product_name": "中式铁锅",
        "product_second_cate_name": "炒锅",
        "share_cnt_7d": "567",
        "share_cnt_all": "6789",
        "shop_id": "12345",
        "shop_name": "小张美食店",
        "video_create_date": "2024-05-01",
        "video_first_tag_name": "美食",
        "video_id": "1234567",
        "video_second_tag_name": "家常菜教程",
        "video_third_tag_name": "家常菜",
        "video_title": "爆款商品推荐",
        "video_url": "https://example.com/video.mp4",
        "vv_pv_7d": "87654"
      }
    ],
    "msg": "xxx"
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
