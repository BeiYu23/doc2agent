# member.JoinShopMemberWithMobileId

> 加入会员接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.JoinShopMemberWithMobileId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/JoinShopMemberWithMobileId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/1806 |
| 更新日期 | `2022-04-29` |

## 接口说明

- 文档书: 会员中心API（版本 V2.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_line` | body | string | 是 | 业务线:电商1 | `1` |
| `inner_shop_id` | body | number | 是 | 店铺号 | `77977` |
| `app_id` | body | number | 是 | 账号组id:抖音固定1128 | `1128` |
| `user_id` | body | number | 是 | 用户号 | `2121` |
| `mobile_id` | body | number | 是 | 手机号id | `2121211` |
| `join_channel` | body | string | 是 | 入会渠道 | `dy_member_microapp` |
| `join_channel_extra` | body | string | 否 | 子渠道:小程序传裂变id | `3232` |
| `biz_desc` | body | string | 否 | 业务描述 | `outer_id` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/JoinShopMemberWithMobileId?app_key=your_appkey_here&method=member.JoinShopMemberWithMobileId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 商家未开通会员功能（sub_code: isv.parameter-invalid:628005200） | 商家未开通会员功能 |
| `20000` | 系统错误 / 请求超时（sub_code: isp.service-error:628004002） | 请求超时 |
| `50002` | 业务处理失败 / 628004401:调用ISV失败（sub_code: isv.business-failed:628004401） | 调用ISV失败 |
| `40004` | 非法的参数 / 628003001:当前手机号码已被他人绑定，请换个号码吧（sub_code: isv.parameter-invalid:628003001） | 当前手机号码已被他人绑定，请换个号码吧 |
| `40004` | 非法的参数 / 628002001:您输入参数不正确，请检查后重试（sub_code: isv.parameter-invalid:628002001） | 参数不正确 |
| `50002` | 业务处理失败 / 628004100:Duplicate entry '(1128,13057269,82231757866)' for key 'PRIMARY'（sub_code: isv.business-failed:628004100） | 业务处理失败 |
| `50002` | 业务处理失败 / 628004000:服务器开小差了，请稍后重试（sub_code: isv.business-failed:628004000） | 服务器开小差 |
| `50002` | 业务处理失败 / 628004103:Query Error: BYTEKV_ERR_CAS_FAILED（sub_code: isv.business-failed:628004103） | 业务处理失败 |
| `50002` | 业务处理失败 / 628004001:RPC通用错误（sub_code: isv.business-failed:628004001） | 请稍后重试 |
| `50002` | 业务处理失败 / 628215028:请求频率受到限制, key=outer_member_point_create_point_account:4597028_1711278893311261（sub_code: isv.business-failed:628215028） | 请求频率受限，请稍后重试 |
| `50002` | 业务处理失败 / 628003005:测试手机号禁止入会线上非测试店铺商家（sub_code: isv.business-failed:628003005） | 628003005:测试手机号禁止入会线上非测试店铺商家 |
| `50002` | 业务处理失败 / 628225002:JoinOuterShopMemberV2 GetLock failed. key=syncJoin:s:4597028_u:95283369217（sub_code: isv.business-failed:628225002） | 628225002:JoinOuterShopMemberV2 GetLock failed. key=syncJoin:s:4597028_u:95283369217 |

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
  "sub_code": "isv.parameter-invalid:628005200",
  "sub_msg": "商家未开通会员功能"
}
```

## 备注
