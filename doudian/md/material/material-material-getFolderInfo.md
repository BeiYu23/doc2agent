# material.getFolderInfo

> 查看文件夹详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.getFolderInfo` |
| 中文名 | 查看文件夹 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/getFolderInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1150 |
| 更新日期 | `2022-12-28` |

## 接口说明

- 文档书: 素材中心API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id` | body | string | 是 | 文件夹id | `70072571115706780601250` |
| `page_num` | body | string | 是 | 分页的页数，从1开始 | `1` |
| `page_size` | body | string | 是 | 每页返回的数量。最大为100，默认为50 | `50` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/getFolderInfo?app_key=your_appkey_here&method=material.getFolderInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `folder_info` | object | 文件夹信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 文件夹ID无效或文件夹已被彻底删除（sub_code: isv.parameter-invalid:20001） | 文件夹id不存或已被彻底删除 |
| `40004` | 非法的参数 / 查询数量超出限制，请通过筛选素材名称/状态/日期等缩小范围（sub_code: isv.parameter-invalid:31002） | 查询数量超出限制，请通过筛选素材名称/状态/日期等缩小范围 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 重试 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10006） | 重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "文件夹ID无效或文件夹已被彻底删除"
}
```

## 备注
