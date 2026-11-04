# second.ecomInsight.createVideoSearchTask

> 创建视频搜索子任务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.createVideoSearchTask` |
| 中文名 | 创建视频搜索子任务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8352 |
| 更新日期 | `2026-06-02` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `video_target` | body | string | 否 | 1. 种草视频 2. 挂车视频 3. 广告视频 | `种草视频` |
| `video_keyword` | body | string | 否 | 视频标题关键词，模糊匹配 | `阳光` |
| `product_keyword` | body | string | 否 | 商品名关键词，模糊匹配 | `牙膏` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 页面条数 | `20` |
| `task_id` | body | mixed | 否 | 主任务id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.createVideoSearchTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `msg` | string | 消息 | `xxx` |
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
      "task_id": "12",
      "task_type": "VideoSearch"
    },
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
