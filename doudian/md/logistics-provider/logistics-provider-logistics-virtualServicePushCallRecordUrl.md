# 通话录音url回传

> logistics.virtualServicePushCallRecordUrl — 通话录音url回传接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 通话录音url回传 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-virtualServicePushCallRecordUrl` |
| 接口 ID | `doudian.logistics-provider.logistics.virtualServicePushCallRecordUrl` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/virtualServicePushCallRecordUrl` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2777 |
| 更新日期 | `2024-12-03` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_code` | body | string | 是 | 供应商唯一标识；需联系群内抖店虚拟号研发配置生成； | `volcengine` |
| `call_id` | body | string | 是 | 供应商通话id，由供应商自定义，需要保持唯一，标识该次通话，幂等； | `xxxxx` |
| `record_url` | body | string | 是 | 供应商通话录音文件url，公网可访问 | `xxxxx` |
| `left_sound_channel_url` | body | string | 否 | 供应商通话录音文件url（左声道），公网可访问 | `xxxxx` |
| `right_sound_channel_url` | body | string | 否 | 供应商通话录音文件url（右声道），公网可访问 | `xxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/virtualServicePushCallRecordUrl?app_key=your_appkey_here&method=logistics.virtualServicePushCallRecordUrl&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
