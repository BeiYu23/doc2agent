# medicine.doctorCloseConsultConversation

> 医生结束问诊会话

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.hospital.medicine.doctorCloseConsultConversation` |
| 中文名 | 医生结束问诊会话 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/doctorCloseConsultConversation` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/5900 |
| 更新日期 | `2023-12-13` |

## 接口说明

- 文档书: 互联网医院（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `consult_id` | body | number | 是 | 问诊单id | `12312321313` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/searchFolder?app_key=your_appkey_here&method=material.searchFolder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000006:系统错误，请稍后重试（sub_code: isv.business-failed:10000006） | 10000006:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / -1:系统错误，请稍后重试（sub_code: isv.business-failed:-1） | -1:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 10000199:系统错误，请稍后重试（sub_code: isv.business-failed:10000199） | 10000199:系统错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "folder_info_list": [
      {
        "create_time": "2020-09-03 18:28:01",
        "delete_time": "2020-09-03 18:28:01",
        "folder_attr": "0",
        "folder_id": "\"70032596029638413241510\"",
        "folder_type": "0",
        "name": "我是文件夹",
        "operate_status": "1",
        "parent_folder_id": "70032596029638413241510",
        "update_time": "2020-09-03 18:28:01"
      }
    ],
    "total": "200"
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
  "sub_code": "isv.business-failed:10000006",
  "sub_msg": "10000006:系统错误，请稍后重试"
}
```

## 备注
