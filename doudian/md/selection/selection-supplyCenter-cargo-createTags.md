# supplyCenter.cargo.createTags

> 针对精选货源所属的货品打标

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.cargo.createTags` |
| 中文名 | 针对精选货源所属的货品打标 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5940 |
| 更新日期 | `2023-12-19` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tags` | body | array | 是 | 要打标的标签列表 | `` |
| `  └ cargo_id` | body | mixed | 是 | 货品ID，相同货品重复打相同tag_code会覆写tag_val | `3631318731020023` |
| `  └ tag_code` | body | string | 是 | 标签名，目前仅支持 DSC_cargo_7day_ret_no_reason = 七天无理由 | `DSC_cargo_7day_ret_no_reason` |
| `  └ tag_val` | body | string | 是 | 标签值，DSC_cargo_7day_ret_no_reason（0-不支持，1-支持） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.createTags&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `failed_tags` | array | 失败的标签 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 内部系统错误（sub_code: isv.business-failed:50002） | 直接重试，覆写即可 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:40002） | 按照报错信息处理 |
| `40004` | 非法的参数 / 不支持的参数（sub_code: isv.parameter-invalid:40004） | 按照报错信息处理 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_tags": [
      {
        "cargo_id": "3631318731020023",
        "tag_code": "DSC_cargo_7day_ret_no_reason"
      }
    ]
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
  "sub_code": "isv.business-failed:50002",
  "sub_msg": "内部系统错误"
}
```

## 备注
