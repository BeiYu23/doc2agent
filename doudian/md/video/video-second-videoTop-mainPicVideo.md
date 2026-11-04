# second.videoTop.mainPicVideo

> 获取主图视频榜单接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.videoTop.mainPicVideo` |
| 中文名 | 获取主图视频榜单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7931 |
| 更新日期 | `2026-01-28` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sort` | body | object | 否 | 排序条件 | `` |
| `  └ field` | body | string | 否 | 排序字段，可使用字段参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `prod_show_uv_30d` |
| `  └ order` | body | string | 否 | 排序方式 asc - 升序， desc - 降序 | `desc` |
| `likes` | body | array | 否 | 搜索条件 | `` |
| `  └ like_value` | body | string | 否 | 搜索方式 | `太阳` |
| `  └ field` | body | string | 否 | 搜索字段，使用方式参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `prod_name` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 条数 | `20` |
| `filters` | body | array | 否 | 过滤条件 | `` |
| `  └ option` | body | string | 否 | 过滤方式，使用方式参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `>300` |
| `  └ field` | body | string | 否 | 过滤字段，可使用字段参考https://bytedance.sg.larkoffice.com/docx/CdM7dD8FVoub3VxpnFdlPk7zglh | `prod_show_pv_30d` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.videoTop.mainPicVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |
| `msg` | string | 返回消息 | `xxxxx` |
| `code` | mixed | 状态码 | `0` |

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
      "page": "1",
      "page_size": "20",
      "records": [
        {
          "id": "1",
          "prod_desc_backup": "xxxxxx",
          "prod_id": "1234565",
          "prod_main_img": "xxxx",
          "prod_name": "xxxx",
          "prod_url": "xxx",
          "screenshot": "xxxxx",
          "shop_name": "xxxx"
        }
      ],
      "total": "20"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
