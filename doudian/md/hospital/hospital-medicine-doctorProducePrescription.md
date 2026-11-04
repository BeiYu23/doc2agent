# medicine.doctorProducePrescription

> 医生开处方单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.hospital.medicine.doctorProducePrescription` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/doctorProducePrescription` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/5901 |
| 更新日期 | `2024-01-17` |

## 接口说明

- 文档书: 互联网医院（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `consult_id` | body | mixed | 是 | 问诊单id | `12321321321321` |
| `produce_time_sec` | body | mixed | 是 | 开方时间（精确到秒） | `//药品信息` |
| `drug_info` | body | array | 是 | 药品信息 | `` |
| `  └ sku_id` | body | mixed | 是 | 药品skuId | `123213213` |
| `  └ doctor_define_num` | body | mixed | 是 | 医生开的药品数量 | `6` |
| `  └ use_info` | body | object | 是 | 使用信息 | `` |
| `    └ use_method` | body | string | 是 | 用法 | `口服` |
| `    └ use_days` | body | mixed | 是 | 使用天数 | `3` |
| `    └ frequency_unit` | body | string | 是 | 频次单位 | `次` |
| `    └ frequency_amount` | body | mixed | 是 | 频次量 | `3` |
| `    └ each_dose` | body | string | 是 | 每次剂量 | `0.5` |
| `    └ perdose_unit` | body | string | 是 | 每次剂量单位 | `片` |
| `doc_practice_cert` | body | string | 是 | 医生执业证编号 | `12321123` |
| `drug_reviewer` | body | string | 是 | 审核药师姓名 | `张小样` |
| `prescription_pic` | body | string | 是 | 处方图片 | `http://xxx.xx.x.com/pic.jpg` |
| `prescription_no` | body | string | 是 | 处方编号(互联网医院定义) | `No.213232232` |
| `diagnostic_result` | body | string | 是 | 诊断结果 | `牙龈炎` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/getFolderInfo?app_key=your_appkey_here&method=material.getFolderInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000004:系统错误，请稍后重试（sub_code: isv.business-failed:10000004） | 10000004:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / -1:系统错误，请稍后重试（sub_code: isv.business-failed:-1） | -1:系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 500013:问诊单无医生接诊（sub_code: isv.business-failed:500013） | 500013:问诊单无医生接诊 |
| `50002` | 业务处理失败 / 50018:开方数量不可小于商品售卖的规格（sub_code: isv.business-failed:50018） | 50018:开方数量不可小于商品售卖的规格 |
| `50002` | 业务处理失败 / 10000006:系统错误，请稍后重试（sub_code: isv.business-failed:10000006） | 10000006:系统错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "folder_info": {
      "child_folder": [
        {
          "create_time": "2021-09-12 12:23:23",
          "delete_time": "2021-09-12 12:23:23",
          "folder_attr": "0",
          "folder_id": "70072571115706780611250",
          "folder_name": "子文件夹名称",
          "folder_type": "0",
          "operate_status": "4",
          "parent_folder_id": "70072571115706780601250",
          "update_time": "2021-09-12 12:23:23"
        }
      ],
      "child_material": [
        {
          "audit_reject_desc": "文件大小超出限制",
          "audit_status": "1",
          "byte_url": "\"\"",
          "create_time": "2021-09-12 12:23:23",
          "delete_time": "0",
          "folder_id": "70072571115706780601250",
          "material_id": "70072571115707435960250",
          "material_type": "photo",
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
            "vid": "123456789",
            "video_cover_url": "https://xxxx.xxx"
          }
        }
      ],
      "create_time": "2021-09-12 12:23:23",
      "delete_time": "0",
      "folder_attr": "0",
      "folder_id": "70072571115706780601250",
      "folder_name": "文件夹名称",
      "folder_type": "0",
      "operate_status": "1",
      "parent_folder_id": "0",
      "total_child_material_num": "12",
      "update_time": "2021-09-12 12:23:23"
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
  "sub_code": "isv.business-failed:10000004",
  "sub_msg": "10000004:系统错误，请稍后重试"
}
```

## 备注
