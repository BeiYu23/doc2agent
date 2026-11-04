# second.videoTop.shortVideo

> 获取短视频榜单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.videoTop.shortVideo` |
| 中文名 | 获取短视频榜单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7932 |
| 更新日期 | `2026-01-30` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `likes` | body | array | 否 | 搜索条件 | `` |
| `  └ like_value` | body | string | 否 | 搜索方式 | `太阳` |
| `  └ field` | body | string | 否 | 搜索字段，使用方式参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `video_title` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 条数 | `20` |
| `filters` | body | array | 否 | 过滤条件 | `` |
| `  └ option` | body | string | 否 | 过滤方式，使用方式参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `<1000` |
| `  └ field` | body | string | 否 | 过滤字段，可使用字段参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `vv_pv_7d` |
| `sort` | body | object | 否 | 排序条件 | `` |
| `  └ order` | body | string | 否 | 排序方式 asc - 升序， desc - 降序 | `desc` |
| `  └ field` | body | string | 否 | 排序字段，可使用字段参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `finish_vv_pv_7d` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.videoTop.shortVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `msg` | string | 消息 | `xxxxx` |
| `code` | mixed | 状态码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 400:（sub_code: isv.business-failed:400） | 查看具体报错，无法解决可提供logid给对应管理员 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "page": "1",
      "page_size": "20",
      "records": [
        {
          "comment_cnt_all": "123",
          "favourite_cnt_all": "123",
          "id": "1",
          "like_cnt_all": "123",
          "product_first_cat_name": "xxxx",
          "product_leaf_cat_name": "xxxx",
          "product_name": "xxxx",
          "product_second_cat_name": "xxxxx",
          "share_cnt_all": "123",
          "shop_name": "xxxx",
          "video_create_date": "xxxx",
          "video_first_tag_name": "xxx",
          "video_id": "123",
          "video_second_tag_name": "xxx",
          "video_third_tag_name": "xxx",
          "video_title": "xxxx",
          "video_url": "xxxx"
        }
      ],
      "total": "4"
    },
    "msg": "xxxxx"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:400",
  "sub_msg": "400:"
}
```

## 备注
