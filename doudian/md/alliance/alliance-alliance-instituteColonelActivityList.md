# alliance.instituteColonelActivityList

> 团长活动查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.instituteColonelActivityList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/instituteColonelActivityList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1330 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V5.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | string | 是 | 活动状态。0：任意状态； 1：未上线； 2：报名未开始； 3：报名中； 4：推广未开始； 5：推广中； 7：报名结束 | `0` |
| `search_type` | body | number | 是 | 排序选项，0:创建时间； 1:活动报名开始时间排序；2:活动报名结束时间排序 | `0` |
| `sort_type` | body | number | 是 | 排序顺序, 0：升序；1：降序 | `0` |
| `page` | body | number | 是 | 页码，从1开始 | `1` |
| `page_size` | body | number | 是 | 每页数量（最大20） | `20` |
| `activity_info` | body | string | 否 | 活动信息，支持通过活动ID和活动名称搜索 | `一个活动` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/instituteColonelActivityList?app_key=your_appkey_here&method=alliance.instituteColonelActivityList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `institution_id` | number | 机构ID | `11111111` |
| `total` | number | 活动条数 | `10` |
| `activity_list` | array | 活动列表 | `` |
| `colonel_buyin_id` | number | 团长百应ID | `46128341673481234` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 根据接口文档检查下入参是否合法 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务内部错误，稍候再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_list": [
      {
        "activity_end_time": "2021-09-02",
        "activity_id": "11111",
        "activity_name": "活动1",
        "activity_start_time": "2021-09-02",
        "application_end_time": "2021-09-02",
        "application_start_time": "2021-09-02",
        "categories_limit": {},
        "status": "1"
      }
    ],
    "colonel_buyin_id": "46128341673481234",
    "institution_id": "11111111",
    "total": "10"
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
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
