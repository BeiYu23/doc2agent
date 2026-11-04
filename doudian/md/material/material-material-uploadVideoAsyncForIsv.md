# isv单个视频上传

> material.uploadVideoAsyncForIsv — isv单个视频上传

| 元信息 | 值 |
| --- | --- |
| 中文名 | isv单个视频上传 |
| 文档地址 | `/docs/doudian/material/material-material-uploadVideoAsyncForIsv` |
| 接口 ID | `doudian.material.material.uploadVideoAsyncForIsv` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/uploadVideoAsyncForIsv` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/3241 |
| 更新日期 | `2023-03-16` |

## 接口说明

- 文档书: 素材中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id` | body | string | 是 | 文件夹id，0为根目录 | `0` |
| `url` | body | string | 否 | 图片url，必须是公网可访问。url和file_uri二选一，不能同时为空，如果2者都不为空取url | `http://xxx.xxx` |
| `name` | body | string | 是 | 视频名称，开发者自定义，不得超过50个字符。 | `视频名称.mp4` |
| `file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `9e1df78157524c63abf7caa9bb1e88e0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/uploadVideoAsyncForIsv?app_key=your_appkey_here&method=material.uploadVideoAsyncForIsv&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | string | 素材id | `7000254886243811628` |
| `folder_id` | string | 素材所在文件夹id，0-素材中心的根目录；其他值-表示对应的文件夹id； | `0` |
| `is_new` | boolean | 是否是新建，true-新建 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 解析素材格式失败（sub_code: isv.parameter-invalid:20001） | 素材的格式不是素材中心支持的 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10003） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 素材库容量不足（sub_code: isv.parameter-invalid:30001） | 删除无用素材 或 联系客服扩容 |
| `40004` | 非法的参数 / 请求已生效，请勿重复请求（sub_code: isv.parameter-invalid:310001） | 并发请求，勿重试 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10004） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 素材涉嫌违规，不能上传（sub_code: isv.parameter-invalid:22007） | 素材涉嫌违规，不能上传 |
| `40004` | 非法的参数 / 素材大小超出限制（sub_code: isv.parameter-invalid:22001） | 素材大小超出限制 |
| `50002` | 业务处理失败 / 素材下载失败，请重新上传（sub_code: isv.business-failed:10010） | 素材下载失败，请重新上传 |

## 响应示例

成功：

```json
{
  "data": {
    "folder_id": "0",
    "is_new": "true",
    "material_id": "7000254886243811628"
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
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "解析素材格式失败"
}
```

## 备注
