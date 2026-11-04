# 根据素材id查素材

> material.queryMaterialDetail — 根据素材id查素材详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据素材id查素材 |
| 文档地址 | `/docs/doudian/material/material-material-queryMaterialDetail` |
| 接口 ID | `doudian.material.material.queryMaterialDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/queryMaterialDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1145 |
| 更新日期 | `2022-12-28` |

## 接口说明

- 文档书: 素材中心API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_id` | body | string | 是 | 素材id；可使用【/material/batchUploadImageSync】【/material/uploadImageSync】【/material/searchMaterial  】接口获取 | `70031975314170022840250` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/queryMaterialDetail?app_key=your_appkey_here&method=material.queryMaterialDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_info` | object | 素材详情 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 素材不存在或已被删除（sub_code: isv.parameter-invalid:22002） | 素材不存在或已被删除 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:20001） | 参数错误 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10004） | 稍后重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:22002",
  "sub_msg": "素材不存在或已被删除"
}
```

## 备注
