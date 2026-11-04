# material.batchUploadImageSync

> 1、一次上传的数量限制50张图片且单个图片最大不能超过10M；   
2、接口上传成功，素材中心会对素材进行异步审核，审核时效：非风险图片99%在4s内完成审核，风险图片我们会在24h内审核完成；对于审核失败的素材，素材中心会在一定时间内将其删除；
3、上

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.batchUploadImageSync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/batchUploadImageSync` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1616 |
| 更新日期 | `2022-12-16` |

## 接口说明

- 文档书: 素材中心API（版本 V3.13）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `materials` | body | array | 是 | 素材信息；一次上传的数量限制50张图片且单个图片最大不能超过10M； | `` |
| `  └ request_id` | body | string | 是 | 该参数仅有2个作用：（1）一次请求中素材的唯一标示；（2）接口防并发，规则是：不同请求所有request_id排序之后拼接起来，若相同视为同一次请求 | `1234567890` |
| `  └ folder_id` | body | string | 是 | 文件夹id，0为素材中心根目录。若想创建文件夹，请参考：https://ehome.bytedance.YOUR_SECRET_KEY?doc=true | `0` |
| `  └ name` | body | string | 是 | 素材名称，长度限制为50个字符 | `这是一个图片` |
| `  └ url` | body | string | 否 | 图片url，必须是公网可访问地址；如果是二进制上传，请使用file_uri字段。url和file_uri二选一，不能同时为空 | `http://xxx/origin` |
| `  └ file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `tos-cn-i-7veqoeduo3/9e1df78157524c63abf7caa9bb1e88e0` |
| `  └ material_type` | body | string | 是 | 素材类型，请传固定值：photo | `photo` |
| `need_distinct` | body | boolean | 否 | 是否去重，默认true:去重，不支持false:不去重，传false无效依旧会去重。去重是指：存在已经审核通过且内容相同的图片，直接返回已存在的图片地址。 | `true` |

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
| `40004` | 非法的参数 / request_id无效（sub_code: isv.parameter-invalid:20002） | 使用有效的request_id |
| `50002` | 业务处理失败 / 请求已生效，请勿重复请求（sub_code: isv.business-failed:31001） | 并发请求，不要重复请求 |
| `40004` | 非法的参数 / 素材数量为空或者超出50个（sub_code: isv.parameter-invalid:20001） | 参数错误 |
| `50002` | 业务处理失败 / 素材库容量不足（sub_code: isv.business-failed:30001） | 联系客服扩容 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10003） | 内部错误，稍后重试 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 素材涉嫌违规，不能上传（sub_code: isv.business-failed:22007） | 素材涉嫌违规，不能上传 |
| `50002` | 业务处理失败 / 存在重复图片，请勿上传重复图片（sub_code: isv.business-failed:31003） | 本次请求中存在重复图片 |
| `50002` | 业务处理失败 / 素材下载失败，请重新上传（sub_code: isv.business-failed:10010） | 重新上传 |
| `40004` | 非法的参数 / 素材大小超出限制（sub_code: isv.parameter-invalid:22001） | 素材大小超出限制，不要重试 |
| `50002` | 业务处理失败 / 已退店商家不支持创建素材/文件夹（sub_code: isv.business-failed:30004） | 请联系客服，不要重复请求 |
| `50002` | 业务处理失败 / 31004:店铺超过每秒上传限制（sub_code: isv.business-failed:31004） | 31004:店铺超过每秒上传限制 |
| `50002` | 业务处理失败 / 22006:当前文件夹下不支持创建该类素材（sub_code: isv.business-failed:22006） | 22006:当前文件夹下不支持创建该类素材 |
| `50002` | 业务处理失败 / 10009:系统异常，请稍后重试（sub_code: isv.business-failed:10009） | 10009:系统异常，请稍后重试 |

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
  "sub_code": "isv.parameter-invalid:20002",
  "sub_msg": "request_id无效"
}
```

## 备注
