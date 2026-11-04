# 专属团长活动商品审核

> alliance.colonelActivityProductAudit — 专属团长活动商品审核接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 专属团长活动商品审核 |
| 文档地址 | `/docs/doudian/alliance/alliance-alliance-colonelActivityProductAudit` |
| 接口 ID | `doudian.alliance.alliance.colonelActivityProductAudit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/colonelActivityProductAudit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/971 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.10）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | number | 是 | 团长活动id | `11111` |
| `apply_ids` | body | array | 是 | 团长商品申请ID。（可在活动商品查询接口中获取） | `[123124,4342311]` |
| `operation` | body | number | 是 | 审核信息（0：通过； 1：拒绝） | `0` |
| `repeat_apply` | body | boolean | 否 | 是否允许二次报名（true:允许，false:不允许） | `true` |
| `suggest_info` | body | string | 否 | 审核建议 | `sakfhkjsd'` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/colonelActivityProductAudit?app_key=your_appkey_here&method=alliance.colonelActivityProductAudit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_audit_info` | array | 审核结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 活动不是处在报名中，不能审核（sub_code: isv.business-failed:4140） | 活动不是处在报名中，不能审核 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 请稍候再试 |
| `50002` | 业务处理失败 / 当前用户不是创建活动的用户（sub_code: isv.business-failed:4139） | 当前用户不是创建活动的用户 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 活动ID不存在（sub_code: isv.business-failed:4138） | 活动ID不存在 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 8192:商品3662679639140211700存在次日生效的费率，请次日再来审批（sub_code: isv.business-failed:8192） | 8192:商品3662679639140211700存在次日生效的费率，请次日再来审批 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "product_audit_info": [
      {
        "apply_id": "111",
        "reject_reason": "商品不在该活动中"
      }
    ]
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
  "sub_code": "isv.business-failed:4140",
  "sub_msg": "活动不是处在报名中，不能审核"
}
```

## 备注
