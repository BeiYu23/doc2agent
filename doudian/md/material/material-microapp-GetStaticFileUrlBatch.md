# ISV批量兑换文件url

> microapp.GetStaticFileUrlBatch — ISV批量兑换文件url

| 元信息 | 值 |
| --- | --- |
| 中文名 | ISV批量兑换文件url |
| 文档地址 | `/docs/doudian/material/material-microapp-GetStaticFileUrlBatch` |
| 接口 ID | `doudian.material.microapp.GetStaticFileUrlBatch` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/microapp/GetStaticFileUrlBatch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/2914 |
| 更新日期 | `2024-12-26` |

## 接口说明

- 文档书: 素材中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_type` | body | mixed | 是 | 选择文件场景， 1：素材中心， 2：TOS临时文件，3: ImageX。 | `2` |
| `path` | body | array | 是 | 文件path路径，请先调用【/microapp/UpdateStaticFileMeta 】上传并审核通过的。 | `["xxx/1.jpg","xxx/2.png"]` |
| `bucket_name` | body | string | 否 | 【目前暂不支持，后续有规划开放】bucket名称，在后端tos场景才需要传 | `your-bucket-name` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/microapp/GetStaticFileUrlBatch?app_key=your_appkey_here&method=microapp.GetStaticFileUrlBatch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `url_map` | string | 文件 信息。 ，  key为path，value为url；注意：批量获取时接口仅返回path路径存在并审核通过的链接，失败的不返回；单个获取时失败返回为空； | `{"xxx/1.jpg":"https://1","xxx/2.png":"https://2"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数有误（sub_code: isv.parameter-invalid:8000002） | 请参考文档填写正确参数 |
| `40004` | 非法的参数 / appKey参数有误（sub_code: isv.parameter-invalid:8000006） | 请填写正确的 appKey |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:8000001） | 联系开放平台同学解决 |

## 响应示例

成功：

```json
{
  "data": {
    "url_map": {}
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
  "sub_code": "isv.parameter-invalid:8000002",
  "sub_msg": "参数有误"
}
```

## 备注
