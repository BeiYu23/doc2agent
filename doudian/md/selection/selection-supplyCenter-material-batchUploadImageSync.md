# supplyCenter.material.batchUploadImageSync

> 精选货源批量上传图片到素材中心

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.material.batchUploadImageSync` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5341 |
| 更新日期 | `2023-11-07` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `materials` | body | array | 是 | 素材信息；一次上传的数量限制50张图片且单个图片最大不能超过10M； | `` |
| `  └ request_id` | body | string | 是 | 该参数仅有2个作用：（1）一次请求中素材的唯一标示；（2）接口防并发，规则是：不同请求所有request_id排序之后拼接起来，若相同视为同一次请求 | `1234567890` |
| `  └ material_type` | body | string | 是 | 素材类型，请传固定值：photo | `photo` |
| `  └ name` | body | string | 是 | 素材名称，长度限制为50个字符 | `这是一个图片` |
| `  └ url` | body | string | 否 | 图片url，必须是公网可访问地址；如果是二进制上传，请使用file_uri字段。url和file_uri二选一，不能同时为空 | `http://xxx/origin` |
| `  └ file_uri` | body | string | 否 | 二进制文件对应的uri，获取方式请参考：https://op.jinritemai.com/docs/guide-docs/171/1719 | `tos-cn-i-7veqoeduo3/9e1df78157524c63abf7caa9bb1e88e0` |
| `need_distinct` | body | boolean | 否 | 是否需要去重（true/false），默认为false。去重是指：存在已经审核通过且内容相同的图片，直接返回已存在的图片地址。 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.material.batchUploadImageSync&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `40004` | 非法的参数 / 参考批量上传图片接口（sub_code: isv.parameter-invalid:40002） | https://op.jinritemai.com/docs/api-docs/69/1616 |
| `50002` | 业务处理失败 / 参考批量上传图片接口（sub_code: isv.business-failed:50002） | https://op.jinritemai.com/docs/api-docs/69/1616 |
| `40004` | 非法的参数 / 参考批量上传图片接口（sub_code: isv.parameter-invalid:40004） | https://op.jinritemai.com/docs/api-docs/69/1616 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_map": {}
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
  "sub_code": "isv.parameter-invalid:40002",
  "sub_msg": "参考批量上传图片接口"
}
```

## 备注
