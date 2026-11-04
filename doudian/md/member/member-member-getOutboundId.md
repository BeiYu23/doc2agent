# 获取外呼id

> member.getOutboundId — 获取外呼id

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取外呼id |
| 文档地址 | `/docs/doudian/member/member-member-getOutboundId` |
| 接口 ID | `doudian.member.member.getOutboundId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/getOutboundId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6114 |
| 更新日期 | `2026-03-17` |

## 接口说明

- 文档书: 会员中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `doudian_open_id` | body | string | 否 | 订单接口返回的doudian_open_id（t+2） | `111` |
| `encrypt_uid` | body | string | 否 | 外呼人群包计划生成的加密外呼ID | `#sdiahdiaihhidhaihiahd` |
| `order_id` | body | string | 否 | 店铺单id | `12312312413` |
| `encrypt_phone` | body | string | 否 | 加密手机号 | `$$sfasef24123$$` |
| `outbound_type` | body | mixed | 否 | 外呼类型 0默认 1教育类(手机号和店铺单id必传) | `1` |
| `doudian_open_id_v2` | body | string | 否 | 订单接口返回的doudian_open_id（实时） | `111` |
| `after_sale_id` | body | string | 否 | 售后单id | `12312312413` |
| `is_downgrade` | body | boolean | 否 | 是否自动降级使用收货人手机号 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/getOutboundId?app_key=your_appkey_here&method=member.getOutboundId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `outbound_id` | string | 外呼id，有效期：1h，人群包外呼ID有效期：24h | `17037442535v6Nz7_3u0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误（sub_code: isv.parameter-invalid:628002001） | 检查入参 |
| `20000` | 系统错误 / 生成outboundId错误（sub_code: isp.service-error:628004920） | 生成outboundId错误，重试或提交工单咨询 |
| `20000` | 系统错误（sub_code: isp.service-error:628004206） | 内部错误，重试或提交工单咨询 |
| `50002` | 业务处理失败 / 火山账号与开发者账号不匹配（sub_code: isv.business-failed:628002004） | 确保火山账号与开发者账号一致 |
| `50002` | 业务处理失败 / 用户非店铺会员（sub_code: isv.business-failed:628003200） | 入参doudian_open_id对应订单用户非店铺会员，无法获取outboundId，建议检查入参信息 |
| `50002` | 业务处理失败 / 628004001:GetUserMobiles failed.（sub_code: isv.business-failed:628004001） | 628004001:GetUserMobiles failed. |
| `50002` | 业务处理失败 / 628004002:RPC超时（sub_code: isv.business-failed:628004002） | 628004002:RPC超时 |
| `50002` | 业务处理失败 / 628004950:member custom qps limit\|cmp.ecom.open_ability:default:lq:\|cmp.ecom.outer_member:default:lq:\|GetUserMobiles\|prod\| onOverQPSLimit, instance=fdbd:dc03:13:945::105,fed-dp-71d4013a60-7c8888b7fb-2hq9w, err_type=limiter_sdk_err_request_limited（sub_code: isv.business-failed:628004950） | 调用频率过高，控制调用QPS |
| `50002` | 业务处理失败 / 628004000:read tcp [fdbd:dc02:ff:2:1:174:80:147]:53986->[fdbd:dc02:d:264::33]:9719: i/o timeout（sub_code: isv.business-failed:628004000） | 系统抖动，稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "outbound_id": "17037442535v6Nz7_3u0"
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
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "入参错误"
}
```

## 备注
