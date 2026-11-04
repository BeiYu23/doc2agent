# 查询定向计划作者列表

> buyin.orienPlanAuthors — 查询定向计划作者列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询定向计划作者列表 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-orienPlanAuthors` |
| 接口 ID | `doudian.alliance.buyin.orienPlanAuthors` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/orienPlanAuthors` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1879 |
| 更新日期 | `2025-03-28` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orien_plan_id` | body | string | 是 | 按定向计划ID搜索 | `1233221` |
| `page` | body | mixed | 否 | 分页，默认 1 | `1` |
| `page_size` | body | mixed | 否 | 每页数目，最大40，默认20 | `20` |
| `audit_status` | body | mixed | 否 | 1 生效中(默认)  2 待审核 3 审核拒绝 | `1` |
| `user_name` | body | string | 否 | 按达人昵称搜索 | `达人昵称` |
| `buyin_id` | body | mixed | 否 | 按达人百应ID搜索 | `111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/orienPlanAuthors?app_key=your_appkey_here&method=buyin.orienPlanAuthors&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 商品定向计划作者数 | `100` |
| `orien_plan_authors` | array | 商品定向计划作者列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效定向计划ID（sub_code: isv.parameter-invalid:4114） | 无效定向计划ID |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 257:参数校验失败（sub_code: isv.business-failed:257） | 257:参数校验失败 |

## 响应示例

成功：

```json
{
  "data": {
    "orien_plan_authors": [
      {
        "apply_id": "1",
        "apply_info": "申请加入",
        "apply_suc_time": "1625480546",
        "apply_time": "1625480546",
        "audit_status": "1",
        "buyin_id": "11111",
        "end_time": "end_time",
        "orien_plan_id": "1233221",
        "user_name": "达人昵称"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:4114",
  "sub_msg": "无效定向计划ID"
}
```

## 备注
