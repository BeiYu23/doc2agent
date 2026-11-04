# medicine.sendMessage

> 医生给用户发送消息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.hospital.medicine.sendMessage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/sendMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/5902 |
| 更新日期 | `2024-01-03` |

## 接口说明

- 文档书: 互联网医院（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `consult_id` | body | number | 是 | 问诊单id | `12312321313123` |
| `chat_type` | body | string | 是 | 消息类型，1:文字、2:图片 | `1` |
| `content` | body | string | 是 | 聊天内容 | `测试` |
| `doc_practice_cert` | body | string | 是 | 医生执业证编号 | `1232321` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/queryMaterialDetail?app_key=your_appkey_here&method=material.queryMaterialDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1:系统错误，请稍后重试（sub_code: isv.business-failed:1） | 1:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 2:系统错误，请稍后重试（sub_code: isv.business-failed:2） | 2:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / -1:系统错误，请稍后重试（sub_code: isv.business-failed:-1） | -1:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 6:系统错误，请稍后重试（sub_code: isv.business-failed:6） | 6:系统错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "material_info": {
      "audit_reject_desc": "文件大小超出限制",
      "audit_status": "5",
      "byte_url": "\"\"",
      "create_time": "2021-09-12 12:23:23",
      "delete_time": "0",
      "folder_id": "70072571115706780601250",
      "material_id": "70072571115707435960250",
      "material_type": "video",
      "materil_name": "名称",
      "operate_status": "0",
      "origin_url": "\"\"",
      "photo_info": {
        "format": "jpg",
        "height": "255",
        "width": "255"
      },
      "size": "1234",
      "update_time": "2021-09-12 12:23:23",
      "video_info": {
        "duration": "12",
        "format": "mp3",
        "height": "32",
        "vid": "12345678",
        "video_cover_url": "www.xxxxxxx.com",
        "width": "23"
      }
    }
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
  "sub_code": "isv.business-failed:1",
  "sub_msg": "1:系统错误，请稍后重试"
}
```

## 备注
