# install.order.supplierAppointment

> 服务商已预约

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.supplierAppointment` |
| 中文名 | 服务商已预约 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/supplierAppointment` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5785 |
| 更新日期 | `2023-12-21` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 实操单号 | `""` |
| `appointment_time` | body | string | 是 | 预约时间，格式："yyyy-MM-dd HH:mm:ss~yyyy-MM-dd HH:mm:ss" | `""` |
| `operation_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `""` |
| `operator_name` | body | string | 否 | 师傅名称 | `""` |
| `operator_phone` | body | string | 否 | 师傅电话，格式，真实号：主机号；虚拟号：主机号-分机号； | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/searchMaterial?app_key=your_appkey_here&method=material.searchMaterial&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000000:请求参数错误（sub_code: isv.business-failed:10000000） | 10000000:请求参数错误 |
| `50002` | 业务处理失败 / 10000006:状态机跃迁校验错误（sub_code: isv.business-failed:10000006） | 10000006:状态机跃迁校验错误 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

## 响应示例

成功：

```json
{
  "data": {
    "material_info_list": [
      {
        "audit_reject_desc": "不符合",
        "audit_status": "1",
        "byte_url": "\\\"\\\"",
        "create_time": "2021-08-12 12:00:12",
        "delete_time": "2021-08-12 12:00:12",
        "folder_id": "6999834643465781548",
        "material_id": "7000291764753940780",
        "material_name": "素材名",
        "material_type": "photo",
        "operate_status": "1",
        "origin_url": "\\\"\\\"",
        "photoInfo": {
          "format": "jpg",
          "height": "255",
          "width": "255"
        },
        "size": "1234",
        "update_time": "2021-08-12 12:00:12",
        "videoInfo": {
          "duration": "12",
          "format": "mp3",
          "height": "23",
          "size": "91226112",
          "vid": "12345678",
          "video_cover_url": "www.xxxxxxx.com",
          "width": "32"
        }
      }
    ],
    "total": "3"
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
  "sub_code": "isv.business-failed:10000000",
  "sub_msg": "10000000:请求参数错误"
}
```

## 备注
