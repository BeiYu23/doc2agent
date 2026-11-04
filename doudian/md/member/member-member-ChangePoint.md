# 会员侧对外积分变更

> member.ChangePoint — 会员侧对外积分变更接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 会员侧对外积分变更 |
| 文档地址 | `/docs/doudian/member/member-member-ChangePoint` |
| 接口 ID | `doudian.member.member.ChangePoint` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/ChangePoint` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/2433 |
| 更新日期 | `2022-08-26` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `app_id` | body | number | 是 | 抖音APPID | `1128` |
| `user_id` | body | number | 是 | 用户ID | `51513211` |
| `op_type` | body | string | 是 | 积分操作类型 1增加 2扣减 | `1` |
| `action_type` | body | string | 是 | 积分操作动作类型 | `9` |
| `amount` | body | number | 是 | 积分操作数量 | `10` |
| `unique_id` | body | string | 是 | 积分操作幂等ID | `2132134432231` |
| `options` | body | object | 否 | 非必需参数 | `` |
| `  └ outer_domain_id` | body | string | 否 | 外域业务ID | `tt5daf2b12c2857910` |
| `member_shop_id` | body | number | 是 | 会员店铺ID | `77977` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/ChangePoint?app_key=your_appkey_here&method=member.ChangePoint&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 积分操作是否成功 | `true` |
| `unique_id` | string | 积分操作幂等ID | `2313141123131` |
| `remark` | string | 积分操作失败原因 | `未找到积分账号数据` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验不合法（sub_code: isv.parameter-invalid:628002001） | 调整参数 |
| `50002` | 业务处理失败 / 下游rpc错误（sub_code: isv.business-failed:628004004） | 下游rpc错误 |
| `20000` | 系统错误 / 下游rpc超时（sub_code: isp.service-error:628004002） | 重试 |
| `50002` | 业务处理失败 / 628215016:未找到积分账号数据（sub_code: isv.business-failed:628215016） | 628215016:未找到积分账号数据 |
| `50002` | 业务处理失败 / 628215028:积分账户写冲突 account_id = 3920750333841424651（sub_code: isv.business-failed:628215028） | 628215028:积分账户写冲突 account_id = 3920750333841424651 |

## 响应示例

成功：

```json
{
  "data": {
    "remark": "未找到积分账号数据",
    "success": "true",
    "unique_id": "2313141123131"
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
  "sub_msg": "参数校验不合法"
}
```

## 备注
