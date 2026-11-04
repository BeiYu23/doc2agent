# 素材中心--素材搜索

> supplyCenter.material.search — 素材中心--素材搜索接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 素材中心--素材搜索 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-material-search` |
| 接口 ID | `doudian.selection.supplyCenter.material.search` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/material/search` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5340 |
| 更新日期 | `2023-11-14` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_id` | body | string | 否 | 素材id | `7000291764753940780` |
| `material_name` | body | string | 否 | 文件名称，支持模糊匹配 | `模糊匹配` |
| `material_type` | body | array | 否 | 素材类型，空-不限； photo-图片；video-视频； | `photo` |
| `operate_status` | body | array | 否 | 素材状态，0-待下载；1-有效；4-回收站中； | `[0,1,4]` |
| `audit_status` | body | array | 否 | 审核状态，1-待审核；2-审核中；3-通过 ；4-拒绝；注意：只有AuditStatus=3时ByteUrl才会返回； | `[1,2,3,4]` |
| `create_time_start` | body | string | 否 | 搜索创建开始时间，格式：yyyy-MM-dd HH:mm:ss | `2022-08-12 12:00:12` |
| `create_time_end` | body | string | 否 | 搜索创建结束时间，格式：yyyy-MM-dd HH:mm:ss | `2022-11-12 12:00:12` |
| `material_id_list` | body | array | 否 | 素材id列表 | `[700029176475394000,700029176475394000]` |
| `page_num` | body | string | 否 | 第几页，1，2，……，默认值：1 | `1` |
| `page_size` | body | string | 否 | 页大小，1，2，……，100，默认值：50 | `20` |
| `order_type` | body | string | 否 | 排序方式，0-按照创建时间倒序 ；1-按照创建时间升序；6-按照素材大小降序；7-按照素材大小升序； | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.material.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_info_list` | array | 素材列表信息 | `` |
| `total` | number | 总数 | `1234` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照查询素材接口（sub_code: isv.parameter-invalid:40002） | https://op.jinritemai.com/docs/api-docs/69/1148 |
| `40004` | 非法的参数 / 参照查询素材接口（sub_code: isv.parameter-invalid:40004） | https://op.jinritemai.com/docs/api-docs/69/1148 |
| `20000` | 系统错误 / 参照查询素材接口（sub_code: isp.service-error:20000） | https://op.jinritemai.com/docs/api-docs/69/1148 |
| `50002` | 业务处理失败 / 参照查询素材接口（sub_code: isv.business-failed:50002） | https://op.jinritemai.com/docs/api-docs/69/1148 |

## 响应示例

成功：

```json
{
  "data": {
    "material_info_list": [
      {
        "audit_reject_desc": "不符合",
        "audit_status": "3",
        "byte_url": "\"\"",
        "create_time": "2021-08-12 12:00:12",
        "delete_time": "2021-08-12 12:00:12",
        "material_id": "7000291764753940000",
        "material_name": "素材名",
        "material_type": "photo",
        "operate_status": "1",
        "origin_url": "\"\"",
        "photo_info": {
          "format": "jpeg",
          "height": "12",
          "width": "12"
        },
        "size": "1234",
        "update_time": "2021-08-12 12:00:12",
        "video_info": {
          "duration": "1234",
          "format": "jpg",
          "height": "12",
          "size": "1234",
          "vid": "12345678",
          "video_cover_url": "www.xxxxxxx.com",
          "width": "12"
        }
      }
    ],
    "total": "1234"
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
  "sub_code": "isv.parameter-invalid:40002",
  "sub_msg": "参照查询素材接口"
}
```

## 备注
