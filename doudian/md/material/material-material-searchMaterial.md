# 不会返回已经删除的素材

> material.searchMaterial — 1、不会返回已经删除的素材；
2、请至少传入一个入参，如果没有任何搜索条件，即：除page_num、page_size、order_type之外的字段都为空，会返【查询失败，未上传任何查询参数】错误。
3、2022年11月-素材接口字段变更公告：https

| 元信息 | 值 |
| --- | --- |
| 中文名 | 不会返回已经删除的素材 |
| 文档地址 | `/docs/doudian/material/material-material-searchMaterial` |
| 接口 ID | `doudian.material.material.searchMaterial` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/searchMaterial` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1148 |
| 更新日期 | `2022-11-17` |

## 接口说明

- 文档书: 素材中心API（版本 V6.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_id` | body | string | 否 | 素材id；可使用【/material/batchUploadImageSync】【/material/uploadImageSync】【/material/searchMaterial  】接口获取 | `7000291764753940780` |
| `material_name` | body | string | 否 | 文件名称，支持模糊匹配 | `模糊匹配,` |
| `material_type` | body | array | 否 | 素材类型，空-不限； photo-图片；video-视频； | `photo` |
| `operate_status` | body | array | 否 | 素材状态，0-待下载；1-有效；4-回收站中； | `[0,1,4]` |
| `audit_status` | body | array | 否 | 审核状态，1-待审核；2-审核中；3-通过 ；4-拒绝；注意：只有AuditStatus=3时ByteUrl才会返回； | `[1,2,3,4]` |
| `create_time_start` | body | string | 否 | 搜索创建开始时间，格式：yyyy-MM-dd HH:mm:ss | `2012-08-12 12:00:12` |
| `create_time_end` | body | string | 否 | 搜索创建结束时间，格式：yyyy-MM-dd HH:mm:ss | `2022-11-12 12:00:12` |
| `folder_id` | body | string | 否 | 文件夹id，0-素材中心； -1-回收站； | `6999834643465781548` |
| `material_id_list` | body | array | 否 | 素材id列表 | `[7000291764753940780,7000291764753940780]` |
| `page_num` | body | string | 否 | 第几页，1，2，……，默认值：1 | `1` |
| `page_size` | body | string | 否 | 页大小，1，2，……，100，默认值：50 | `20` |
| `order_type` | body | string | 否 | 排序方式，0-按照创建时间倒序 ；1-按照创建时间升序；6-按照素材大小降序；7-按照素材大小升序； | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_info_list` | array | 素材列表信息 | `` |
| `total` | number | 总数 | `3` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 文件夹ID错误，请输入正确的文件夹ID（sub_code: isv.parameter-invalid:20001） | 文件夹id不正确 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10003） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 查询数量超出限制，请通过筛选素材名称/状态/日期等缩小范围（sub_code: isv.parameter-invalid:31002） | 查询数量超出限制，请通过筛选素材名称/状态/日期等缩小范围 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10006） | 系统异常，请稍后重试 |

## 响应示例

成功：

```json
{
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
  "sub_msg": "文件夹ID错误，请输入正确的文件夹ID"
}
```

## 备注
