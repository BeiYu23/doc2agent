# shopVideo.reportVideoPublishRecord

> 上报短视频上传记录

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.reportVideoPublishRecord` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/reportVideoPublishRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7970 |
| 更新日期 | `2025-12-19` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `item_id` | body | number | 是 | 短视频ID | `1872068485345111` |
| `user_id` | body | number | 否 | 作者账号id（抖音uid），不传默认人店一体账号，支持渠道号 | `7553945164076821278` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolLiveShare?app_key=your_appkey_here&method=buyin.kolLiveShare&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否上报成功 | `false` |
| `failed_reason` | string | 上报失败原因 | `userID与店铺的关联关系不存在` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
