# yunc.uploadErpFile

> erp系统上传商货关系文件服务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.uploadErpFile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/uploadErpFile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/4523 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bin_file_uri` | body | string | 是 | 文件资源描述符 | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |
| `name` | body | string | 是 | 20130702_APPID_文件总数_第几个文件 | `20130702_123456789065_06_01` |
| `idempotent` | body | string | 是 | 文件唯一标识 | `azazazaaaa22` |
| `line_number` | body | mixed | 是 | 文件行数 | `100000` |
| `file_md5` | body | string | 是 | 文件md5值 | `xxxxxxxx` |
| `file_number` | body | mixed | 是 | 文件数目 | `5` |
| `total_line_number` | body | mixed | 是 | 总行数 | `10000` |
| `bin_original_uri` | body | string | 是 | 和bin_file_uri的值一样 | `/tos-cn-i-7veqoeduo3/2b2acab2be994a77bcced42475523d67` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/uploadErpFile?app_key=your_appkey_here&method=yunc.uploadErpFile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 错误编码 | `111` |
| `msg` | string | 错误描述 | `参数非法` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:30001） | 核对请求入参数 |
| `50002` | 业务处理失败 / 验签失败,请检查参数（sub_code: isv.business-failed:30002） | 验签失败,请检查参数 |
| `50002` | 业务处理失败 / 文件重复，无需上传（sub_code: isv.business-failed:30003） | 文件重复，无需上传 |
| `50002` | 业务处理失败 / 业务处理错误,请联系客服（sub_code: isv.business-failed:30004） | 业务处理错误,请联系客服 |
| `50002` | 业务处理失败 / 文件行数不一致，请检查（sub_code: isv.business-failed:30005） | 文件行数不一致，请检查 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "111",
    "msg": "参数非法"
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
  "sub_code": "isv.parameter-invalid:30001",
  "sub_msg": "参数错误"
}
```

## 备注
