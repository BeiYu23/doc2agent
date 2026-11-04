# 团长活动特殊申请审核

> buyin.colonel.specialApplyDeal — 团长活动特殊申请审核

| 元信息 | 值 |
| --- | --- |
| 中文名 | 团长活动特殊申请审核 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-colonel-specialApplyDeal` |
| 接口 ID | `doudian.alliance.buyin.colonel.specialApplyDeal` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonel/specialApplyDeal` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1553 |
| 更新日期 | `2022-09-27` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | number | 是 | 活动ID | `12312` |
| `product_id` | body | number | 是 | 商品ID | `2312312312312` |
| `special_apply_id` | body | number | 是 | 特殊申请ID | `23123` |
| `status` | body | string | 是 | 处理结果。1：同意；  2：拒绝 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 审批是否成功，true 为成功，false 为失败（即使团长同意，但是不满足条件也会自动拒绝） | `true` |
| `low_service_fee_activity_id` | array | 活动 ID 列表（当商品提报了二级团长时,商家申请降低服务费率，若调整的服务费率*90%后的值，低于任意一个一级团长报名的二级团长服务费率，当一级团长点击同意时，系统自动拒绝，并且告知不合条件的活动ID） | `31212` |
| `second_activity_id` | array | 活动 ID 列表（当商品提报了二级团长时，不允许降低佣金率，当一级团长点击同意时，系统自动拒绝，并且告知所有合作中的二级活动 ID） | `54212` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 已经处理过该申请，无需重复处理（sub_code: isv.business-failed:100010） | 已经处理过该申请，无需重复处理 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 服务器错误，请稍后再试（sub_code: isv.business-failed:500） | 服务器错误，请稍后再试 |
| `50002` | 业务处理失败 / 已经处理过该申请，无需重复处理（sub_code: isv.business-failed:8192） | 已经处理过该申请，无需重复处理 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:100010",
  "sub_msg": "已经处理过该申请，无需重复处理"
}
```

## 备注
