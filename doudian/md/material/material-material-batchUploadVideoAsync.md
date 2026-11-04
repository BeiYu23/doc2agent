# material.batchUploadVideoAsync

> 批量上传视频到素材中心

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.batchUploadVideoAsync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/batchUploadVideoAsync` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1617 |
| 更新日期 | `2022-10-11` |

## 接口说明

- 文档书: 素材中心API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `materials` | body | array | 是 | 素材信息 | `` |
| `  └ request_id` | body | string | 是 | 该参数仅有2个作用：（1）一次请求中素材的唯一标示；（2）接口防并发，规则是：不同请求所有request_id排序之后拼接起来，若相同视为同一次请求 | `123456789` |
| `  └ folder_id` | body | string | 是 | 文件夹id，“0”为素材中心根目录。若想创建文件夹，请参考：https://ehome.bytedance.YOUR_SECRET_KEY?doc=true | `0` |
| `  └ name` | body | string | 是 | 素材名称，长度限制为50个字符，最好带上后缀 | `这是一个视频.mp4` |
| `  └ url` | body | string | 否 | 视频url。如果是二进制上传，请使用file_uri字段。url和file_uri二选一，不能同时为空 | `https://origin/xxxx` |
| `  └ file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `tos-cn-i-7veqoeduo3/9e1df78157524c63abf7caa9bb1e88e0` |
| `  └ material_type` | body | string | 是 | 素材类型，请传固定值：video | `video` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_map` | string | 成功上传的素材，key为参数中的request_id | `` |
| `failed_map` | string | 失败的素材，key为参数中的request_id | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 参数错误（sub_code: isp.service-error:20001） | 检查参数 |
| `50002` | 业务处理失败 / 30001:素材库容量不足（sub_code: isv.business-failed:30001） | 30001:素材库容量不足 |
| `50002` | 业务处理失败 / 22006:当前文件夹下不支持创建该类素材（sub_code: isv.business-failed:22006） | 22006:当前文件夹下不支持创建该类素材 |
| `50002` | 业务处理失败 / 31001:请求已生效，请勿重复请求（sub_code: isv.business-failed:31001） | 31001:请求已生效，请勿重复请求 |
| `50002` | 业务处理失败 / 22001:素材大小超出限制，图片限10M、视频限200M（sub_code: isv.business-failed:22001） | 22001:素材大小超出限制，图片限10M、视频限200M |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:20001",
  "sub_msg": "参数错误"
}
```

## 备注
