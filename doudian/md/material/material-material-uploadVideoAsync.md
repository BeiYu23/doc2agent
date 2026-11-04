# 素材中心--异步上传视频

> material.uploadVideoAsync — 素材中心--异步上传视频接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 素材中心--异步上传视频 |
| 文档地址 | `/docs/doudian/material/material-material-uploadVideoAsync` |
| 接口 ID | `doudian.material.material.uploadVideoAsync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/uploadVideoAsync` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1147 |
| 更新日期 | `2022-10-11` |

## 接口说明

- 文档书: 素材中心API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id` | body | string | 是 | 父文件夹id，0为根目录。若需要创建文件夹，请参考：https://ehome.bytedance.YOUR_SECRET_KEY?doc=true | `0` |
| `url` | body | string | 否 | 视频url，url和file_uri二选一，不能同时为空，如果2者都传则取url | `https://xxxx.xxx.xx` |
| `name` | body | string | 是 | 视频名称，不得超过50个字符，最好带上后缀 | `视频.mp4` |
| `file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `tos-cn-i-7veqoeduo3/9e1df78157524c63abf7caa9bb1e88e0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | string | 素材id | `7000254886243811628` |
| `folder_id` | string | 素材所在文件夹id，0-素材中心的根目录 | `0` |
| `is_new` | boolean | 是否是新建，false-重复请求 true-新建 | `true` |
| `audit_status` | string | 素材审核状态 0-下载中 1-等待审核 2-审核中 3-通过 4-拒绝 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:20001） | 请检查参数 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10004） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 素材大小超出限制（sub_code: isv.parameter-invalid:22001） | 视频大小超出限制，勿重复操作 |
| `40004` | 非法的参数 / 请求已生效，请勿重复请求（sub_code: isv.parameter-invalid:31001） | 并发请求导致，请稍后重试 |
| `40004` | 非法的参数 / 素材库容量不足（sub_code: isv.parameter-invalid:30001） | 容量不足，删除部分素材后重试 |
| `50002` | 业务处理失败 / 素材下载失败，请重新上传（sub_code: isv.business-failed:10010） | 素材下载失败，请重新上传 |
| `50002` | 业务处理失败 / 31004:店铺超过每秒上传限制（sub_code: isv.business-failed:31004） | 31004:店铺超过每秒上传限制 |
| `50002` | 业务处理失败 / 22006:当前文件夹下不支持创建该类素材（sub_code: isv.business-failed:22006） | 22006:当前文件夹下不支持创建该类素材 |

## 响应示例

成功：

```json
{
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
  "sub_msg": "参数错误"
}
```

## 备注
