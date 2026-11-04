# 搜索文件夹

> material.searchFolder — 搜索文件夹

| 元信息 | 值 |
| --- | --- |
| 中文名 | 搜索文件夹 |
| 文档地址 | `/docs/doudian/material/material-material-searchFolder` |
| 接口 ID | `doudian.material.material.searchFolder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/searchFolder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1149 |
| 更新日期 | `2022-12-28` |

## 接口说明

- 文档书: 素材中心API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_by` | body | string | 是 | 排序方式 0-创建时间倒序 1-创建时间正序 2-修改时间倒序 3-修改时间正序 4-文件夹名倒序 5-文件夹名正序 | `1` |
| `page_num` | body | string | 是 | 分页的页数，从1开始 | `1` |
| `page_size` | body | string | 是 | 每页返回的数量。最大为100，默认为50 | `40` |
| `name` | body | string | 否 | 需要搜索的文件名片段 | `图片` |
| `folder_id` | body | string | 否 | 文件夹id | `"70032596029638413241510"` |
| `create_time_start` | body | string | 否 | 创建时间最小值，包含这一秒 | `2020-09-03 18:28:00` |
| `create_time_end` | body | string | 否 | 创建时间最大值，包含这一秒 | `2020-09-03 18:28:01` |
| `parent_folder_id` | body | string | 否 | 父文件夹id | `"70032596029638413241510"` |
| `operate_status` | body | array | 否 | 文件夹状态。1-有效 4-在回收站中 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/searchFolder?app_key=your_appkey_here&method=material.searchFolder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `folder_info_list` | array | 文件夹列表 | `` |
| `total` | number | 符合筛选条件的文件夹数量 | `200` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 文件夹ID无效或文件夹已被彻底删除（sub_code: isv.parameter-invalid:20001） | 文件夹不存在的原因有：（1）主从延迟导致；（2）已被删除 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 系统异常，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10006） | 系统异常，请稍后重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "文件夹ID无效或文件夹已被彻底删除"
}
```

## 备注
