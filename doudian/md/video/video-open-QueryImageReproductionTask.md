# 查询图片复刻任务

> open.QueryImageReproductionTask — 查询图片复刻任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询图片复刻任务 |
| 文档地址 | `/docs/doudian/video/video-open-QueryImageReproductionTask` |
| 接口 ID | `doudian.video.open.QueryImageReproductionTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/QueryImageReproductionTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8595 |
| 更新日期 | `2026-09-09` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `body` | body | string | 否 | 入参原样透传(raw JSON 字符串) | `{"xx": "xx"}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/QueryImageReproductionTask?app_key=your_appkey_here&method=open.QueryImageReproductionTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 下游响应体原样透传(raw JSON 字符串) | `QueryImageReproductionTask` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "QueryImageReproductionTask"
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
