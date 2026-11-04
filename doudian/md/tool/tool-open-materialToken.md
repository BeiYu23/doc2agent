# open.materialToken

> 素材上传接口访问token

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.materialToken` |
| 中文名 | 素材上传接口访问token |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/materialToken` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/2222 |
| 更新日期 | `2024-09-04` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `upload_num` | body | mixed | 是 | 需要上传的素材数量 | `2` |
| `file_extension` | body | string | 否 | 文件后缀名称，必须以"."开头 | `.xlsx` |
| `biz_type` | body | mixed | 否 | 业务类型，  1: 素材中心 。 2: ImageX | `2` |
| `store_keys_array_json` | body | string | 否 | 当 biz_type 为 2，则可以自定义路径名 | `666/1.jpg` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/materialToken?app_key=your_appkey_here&method=open.materialToken&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `auth_query` | string | 获取下载地址query | `https://imagex.bytedanceapi.com/?Action=ApplyImageUpload&FileExtension=.jpg&ServiceId=0cskzgtrpl&StoreKeys=6864478719709300238%2F666%2F1.jpg&UploadNum=1&Version=2018-08-01&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=YOUR_ACCESS_KEY_ID%2F20230216%2Fcn-north-1%2FImageX%2Faws4_request&X-Amz-Date=20230216T091632Z&X-Amz-Expires=180&X-Amz-NotSignBody=&X-Amz-Signature=f549fadb3d1a98f04c8d29859361957e899323de76dd56bbdcf4379424cc3bb8&X-Amz-SignedHeaders=&X-Amz-SignedQueries=Action%3BFileExtension%3BServiceId%3BStoreKeys%3BUploadNum%3BVersion%3BX-Amz-Algorithm%3BX-Amz-Credential%3BX-Amz-Date%3BX-Amz-Expires%3BX-Amz-NotSignBody%3BX-Amz-SignedHeaders%3BX-Amz-SignedQueries` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 100000:参数错误（sub_code: isv.business-failed:100000） | 联系开放平台同学 |

## 响应示例

成功：

```json
{
  "data": {
    "auth_query": "https://imagex.bytedanceapi.com/?Action=ApplyImageUpload&FileExtension=.jpg&ServiceId=0cskzgtrpl&StoreKeys=6864478719709300238%2F666%2F1.jpg&UploadNum=1&Version=2018-08-01&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=YOUR_ACCESS_KEY_ID%2F20230216%2Fcn-north-1%2FImageX%2Faws4_request&X-Amz-Date=20230216T091632Z&X-Amz-Expires=180&X-Amz-NotSignBody=&X-Amz-Signature=f549fadb3d1a98f04c8d29859361957e899323de76dd56bbdcf4379424cc3bb8&X-Amz-SignedHeaders=&X-Amz-SignedQueries=Action%3BFileExtension%3BServiceId%3BStoreKeys%3BUploadNum%3BVersion%3BX-Amz-Algorithm%3BX-Amz-Credential%3BX-Amz-Date%3BX-Amz-Expires%3BX-Amz-NotSignBody%3BX-Amz-SignedHeaders%3BX-Amz-SignedQueries"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:100000",
  "sub_msg": "100000:参数错误"
}
```

## 备注
