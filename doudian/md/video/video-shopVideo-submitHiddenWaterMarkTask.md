# 提交加暗水印任务

> shopVideo.submitHiddenWaterMarkTask — 提交加暗水印任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 提交加暗水印任务 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-submitHiddenWaterMarkTask` |
| 接口 ID | `doudian.video.shopVideo.submitHiddenWaterMarkTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/submitHiddenWaterMarkTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7208 |
| 更新日期 | `2025-01-15` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `mediaId` | body | string | 否 | 通过sdk上传后的获取到的mediaId，url和mediaId必须传一个 | `v0d27cg10001csve2qfog65o283c1h0g` |
| `url` | body | string | 否 | 视频url，必须公网可访问，url和mediaId必须传一个，优先mediaId | `https://v3-cold.douyinvod.com/b6fb2946ffc92fb4e` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/submitHiddenWaterMarkTask?app_key=your_appkey_here&method=shopVideo.submitHiddenWaterMarkTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_id` | string | 任务id | `7458213968494985526` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:605025001） | 根据异常描述调整参数 |
| `50002` | 业务处理失败 / vod上传授权失败（sub_code: isv.business-failed:605025002） | 请稍后重试 |
| `20000` | 系统错误 / 数据存储失败（sub_code: isp.service-error:605025004） | 请稍后重试 |
| `50002` | 业务处理失败 / 视频url不合法（sub_code: isv.business-failed:605025007） | 检查视频url |
| `50002` | 业务处理失败 / 转码失败（sub_code: isv.business-failed:605025010） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "task_id": "7458213968494985526"
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
  "sub_code": "isv.parameter-invalid:605025001",
  "sub_msg": "参数错误"
}
```

## 备注
