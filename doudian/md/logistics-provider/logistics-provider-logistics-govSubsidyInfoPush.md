# 国补拍照信息回传

> logistics.govSubsidyInfoPush — 国补拍照信息回传接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 国补拍照信息回传 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-govSubsidyInfoPush` |
| 接口 ID | `doudian.logistics-provider.logistics.govSubsidyInfoPush` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/govSubsidyInfoPush` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7492 |
| 更新日期 | `2026-03-13` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fulfillment_finish` | body | boolean | 否 | 是否履约 | `false` |
| `correct_finish` | body | boolean | 否 | 是否正常完成任务 | `false` |
| `sn_code` | body | string | 否 | snCode | `123` |
| `imei_code` | body | string | 否 | imeiCode | `123` |
| `track_no` | body | string | 否 | 运单号 | `1231231` |
| `finish_timestamp` | body | mixed | 否 | 任务完成时间 | `1747896088` |
| `reason_type` | body | string | 否 | 失败原因类型 | `123` |
| `photo_list` | body | array | 否 | 照片列表 | `` |
| `  └ photo_type` | body | string | 否 | 照片类型 | `1` |
| `  └ photo_url` | body | string | 否 | 支持下载的图片url | `可下载的链接` |
| `imei_code2` | body | string | 否 | imeiCode2 | `imeiCode2` |
| `start_timestamp` | body | mixed | 否 | 任务开始时间 | `开始时间` |
| `sn_code_list` | body | array | 否 | sn_code列表 | `` |
| `  └ sn_code` | body | string | 否 | snCode | `snCode` |
| `  └ sn_code_type` | body | string | 否 | sn类型 | `Outdoor` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/govSubsidyInfoPush?app_key=your_appkey_here&method=logistics.govSubsidyInfoPush&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | boolean | 请求是否成功 | `true` |
| `return_code` | mixed | 返回码 | `0` |
| `message` | string | 错误信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "message": "成功",
    "result": "true",
    "return_code": "0"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
