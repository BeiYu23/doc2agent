# 创建素材任务

> second.ecomInsight.createAssetTask — 创建素材任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建素材任务 |
| 文档地址 | `/docs/doudian/video/video-second-ecomInsight-createAssetTask` |
| 接口 ID | `doudian.video.second.ecomInsight.createAssetTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8183 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | 任务名 | `xxx` |
| `url` | body | string | 否 | 传入图像、音频、视频素材时，仅支持上传 URL ，不支持 base64。 将人脸、服装细节单独分割出来，作为单独的图片传给模型，可以有效避免参考不准的问题，具体可参考如下规则及示例： 传入单个图像要求 - 格式：jpeg、png、webp、bmp、tiff、gif、heic/heif - 宽高比（宽/高）： (0.4, 2.5)  - 宽高长度（px）：(300, 6000) - 大小：单张图片小于 30 MB 传入单个视频要求 - 格式：mp4、mov - 分辨率：480p、720p - 时长：单个视频时长 [2, 15] s - 尺寸：   - 宽高比（宽/高）：[0.4, 2.5]   - 宽高长度（px）：[300, 6000]   - 总像素数：[640×640=409600, 834×1112=927408]，即宽和高的乘积符合 [409600, 927408] 的区间要求。 - 大小：单个视频不超过 50 MB - 帧率 (FPS)：[24, 60]  传入单个音频要求 - 格式：wav、mp3 - 时长：单个音频时长 [2, 15] s - 大小：单个音频不超过 15 MB | `xxxx` |
| `asset_type` | body | string | 否 | Image、Video、Audio | `Image` |
| `group_id` | body | string | 否 | 活体对应group_id | `xxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.createAssetTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回对象 | `` |
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
      "task_id": "12312"
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
