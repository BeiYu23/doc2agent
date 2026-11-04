# material.uploadImageSync

> 素材中心同步创建图片素材接口
1、如需上传多个素材，请使用批量上传图片接口：【/material/batchUploadImageSync】且单个图片最大不能超过10M；支持的格式有：png/jpg；
3、接口上传成功，素材中心会对素材进行异步审核，审核时

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.uploadImageSync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/uploadImageSync` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1146 |
| 更新日期 | `2024-06-11` |

## 接口说明

- 文档书: 素材中心API（版本 V7.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id` | body | string | 是 | 文件夹id，0为根目录 | `2` |
| `url` | body | string | 否 | 图片url，必须是公网可访问。url和file_uri二选一，不能同时为空，如果2者都不为空取url | `http://xxx.xxx` |
| `material_name` | body | string | 是 | 图片名称，开发者自定义，不得超过50个字符。 | `图片名称.jpg` |
| `file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `tos-cn-i-7veqoeduo3/9e1df78157524c63abf7caa9bb1e88e0` |
| `need_distinct` | body | boolean | 否 | 是否去重，默认true:去重，不支持false:不去重，传false无效依旧会去重。去重是指：存在已经审核通过且内容相同的图片，直接返回已存在的图片地址。 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | string | 素材id；MaterialId调用【/material/queryMaterialDetail】接口，当audit_status=3时获取byte_url； | `7000254886243811628` |
| `folder_id` | string | 素材所在文件夹id，0-素材中心的根目录；其他值-表示对应的文件夹id； | `2` |
| `is_new` | boolean | 是否是新建，true-新建 | `true` |
| `audit_status` | string | 素材审核状态; 1-等待审核; 2-审核中; 3-通过; 4-拒绝;注意：只有AuditStatus=3时ByteUrl才会返回； | `2` |
| `byte_url` | string | 【已下线】新的URL可使用下列方式获取：方式一：可监听【店铺使用doudian_material_auditResultForShop】或【供应商使用doudian_material_auditResultForBSCP】audit_status=3时可以使用byte_url；方式二：根据响应参数MaterialId调用【/material/queryMaterialDetail】接口，当audit_status=3时获取byte_url； | `https://xxx.xx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 解析素材格式失败（sub_code: isv.parameter-invalid:20001） | 素材的格式不是素材中心支持的 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10003） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 素材库容量不足（sub_code: isv.parameter-invalid:30001） | 联系客服扩容 |
| `40004` | 非法的参数 / 请求已生效，请勿重复请求（sub_code: isv.parameter-invalid:31001） | 并发请求，勿重试 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10004） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 素材涉嫌违规，不能上传（sub_code: isv.business-failed:22007） | 素材涉嫌违规，不能上传 |
| `50002` | 业务处理失败 / 存在重复图片，请勿上传重复图片（sub_code: isv.business-failed:31003） | 同一个请求中，存在重复图片 |
| `50002` | 业务处理失败 / 素材大小超出限制（sub_code: isv.business-failed:22001） | 素材大小超出限制 |
| `50002` | 业务处理失败 / 素材下载失败，请重新上传（sub_code: isv.business-failed:10010） | 素材下载失败，请重新上传 |
| `50002` | 业务处理失败 / 当前文件夹下不支持创建该类素材（sub_code: isv.business-failed:22006） | 请确定文件夹属性是否支持上传图片 |
| `50002` | 业务处理失败 / 30004:已退店商家不支持创建素材/文件夹（sub_code: isv.business-failed:30004） | 请检查店铺状态 |
| `50002` | 业务处理失败 / 31004:店铺超过每秒上传限制（sub_code: isv.business-failed:31004） | 31004:店铺超过每秒上传限制 |
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
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "解析素材格式失败"
}
```

## 备注
