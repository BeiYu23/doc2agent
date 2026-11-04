# 创建视频推荐子任务

> second.ecomInsight.createVideoRecommendTask — 创建视频推荐子任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建视频推荐子任务 |
| 文档地址 | `/docs/doudian/video/video-second-ecomInsight-createVideoRecommendTask` |
| 接口 ID | `doudian.video.second.ecomInsight.createVideoRecommendTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8355 |
| 更新日期 | `2026-07-07` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 页面条数 | `20` |
| `task_id` | body | mixed | 否 | 任务id | `123` |
| `product_id` | body | string | 否 | 商品id | `xxxx` |
| `product_title` | body | string | 否 | 商品标题 | `xxxx` |
| `product_image_url` | body | string | 否 | 商品图片链接，必须是公网可访问的 | `xxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.createVideoRecommendTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `msg` | string | 消息 | `xxxx` |
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
      "id": "123",
      "task_id": "1",
      "task_type": "VideoRecommending"
    },
    "msg": "xxxx"
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
