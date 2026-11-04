# 查询加暗水印任务

> shopVideo.getHiddenWaterMarkTask — 查询加暗水印任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询加暗水印任务 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-getHiddenWaterMarkTask` |
| 接口 ID | `doudian.video.shopVideo.getHiddenWaterMarkTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/getHiddenWaterMarkTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7207 |
| 更新日期 | `2025-01-15` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_id` | body | string | 是 | 任务id | `7458213968494985526` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/getHiddenWaterMarkTask?app_key=your_appkey_here&method=shopVideo.getHiddenWaterMarkTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `watermark_url` | string | 加完暗水印后的资源url，在status=3时有值，注意：该url有效期10分钟，禁止对外暴露，请在自己系统内转储后给商家播放/下载 | `https://v3-cold.douyinvod.com/b6fb2946ffc92fb4e` |
| `task_id` | string | 任务id | `7458213968494985526` |
| `display_status` | mixed | 任务状态：1：上传视频中，2-加暗水印中，3：任务成功，4：任务失败 | `3` |
| `failed_reason` | string | 失败原因，在task_status=4时有值 | `系统异常` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 根据异常描述调整参数 |

## 响应示例

成功：

```json
{
  "data": {
    "display_status": "3",
    "failed_reason": "系统异常",
    "task_id": "7458213968494985526",
    "watermark_url": "https://v3-cold.douyinvod.com/b6fb2946ffc92fb4e"
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
