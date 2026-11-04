# second.ecomInsight.createVideoSearchTopTask

> 创建视频查询榜单任务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.createVideoSearchTopTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8378 |
| 更新日期 | `2026-07-23` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `likes` | body | array | 否 | 模糊搜索 | `` |
| `  └ field` | body | string | 否 | 搜索字段 | `video_title` |
| `  └ like_value` | body | string | 否 | 对应搜索值 | `阳光` |
| `task_id` | body | mixed | 否 | 任务id | `123` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 每页条数最多30条 | `30` |
| `filters` | body | array | 否 | 筛选条件 | `` |
| `  └ field` | body | string | 否 | 筛选字段 | `product_first_cat_name` |
| `  └ option` | body | string | 否 | 筛选方式 | `药品` |
| `sort` | body | object | 否 | 排序条件 | `` |
| `  └ order` | body | string | 否 | 排序方式 | `desc` |
| `  └ field` | body | string | 否 | 排序字段 | `vv_pv_7d` |
| `not_likes` | body | array | 否 | 模糊搜索排除 | `` |
| `  └ field` | body | string | 否 | 搜索字段 | `video_title` |
| `  └ like_value` | body | string | 否 | 对应搜索值 | `阳光` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.createVideoSearchTopTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `msg` | string | 消息体 | `xxx` |
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
      "id": "xxxx",
      "task_id": "xxxx",
      "task_type": "xxxx"
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
