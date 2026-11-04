# member.batchUpdate

> 会员数据更新接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.batchUpdate` |
| 中文名 | 会员数据更新 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/batchUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/329 |
| 更新日期 | `2024-07-22` |

## 接口说明

- 文档书: 会员中心API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `app_id` | body | mixed | 是 | 表明外部平台 | `1` |
| `member_info_list` | body | array | 是 | 新的用户数据，数组中一次最多可更新5个用户的信息 | `` |
| `  └ birthday` | body | string | 否 | 会员生日，格式：月-日，如08-08 | `08-08` |
| `  └ open_id` | body | string | 是 | 会员对外的身份ID | `cb7bf7efa6d652046abd2f7d84ee18c1` |
| `  └ mobile` | body | string | 否 | 新的手机号 | `15012345678` |
| `  └ level` | body | mixed | 否 | 新的等级 | `1` |
| `  └ unbind` | body | boolean | 否 | 是否解绑 | `true` |
| `  └ integral` | body | mixed | 否 | 已废弃，仅支持存量历史商家】用户最新积分，正数表示法。如果有小数或者负数诉求的必须对接PointCent字段。新商家考虑扩展性，都建议对接PointCent。PointCent设置值时，优先级比Integral高 | `100` |
| `  └ pointCent` | body | mixed | 否 | 【推荐】用户最新积分，分表示法，会乘以100放大，目前最多支持两位小数，同时也支持负数，PointCent=100表示1积分，PointCent=-111表示-1.11积分 | `11100` |
| `  └ union_id` | body | string | 否 | 【仅品牌会员通商家设置】品牌会员的union_id，可此以此来标识某一个用户。（商家在抖店企业版配置同品牌跨店互通配置） | `#YOUR_SECRET_KEY` |
| `  └ cancel` | body | boolean | 否 | 【仅测试商家使用】是否注销，区别于上面的解绑动作，注销操作会清空用户历史绑定信息，影响用户开卡礼等权益领取判断。目前灰度测试中，如有必要使用，需提报会员通运营审批后使用。 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/batchUpdate?app_key=your_appkey_here&method=member.batchUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `batch_update_response_info` | array | 更新用户的信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 网络错误，请稍后再试~（sub_code: isp.service-error:628145000） | 请稍后再试 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:628002001） | 请查看操作接口返回的详细错误描述，针对性的调整错误参数 |
| `50002` | 业务处理失败 / 请求过于频繁，请稍后重试（sub_code: isv.business-failed:628145015） | 请检查短时间内是否并发操作同账号？请检查是否和平台SPI请求并发？ |
| `40004` | 非法的参数 / openId非法（sub_code: isv.parameter-invalid:628145003） | 请检查传入的open_id和token店铺ID是否有关联？确认openId是否合法？ |
| `50002` | 业务处理失败 / 【抖店会员体系升级会员通体系】会员数据传输中，请勿更新会员数据。（sub_code: isv.business-failed:628145010） | 等待升级完成。如有疑问，请联系商家IT或者服务商技术同学咨询 |
| `50002` | 业务处理失败 / 抖店会员商家不允许更新用户信息（sub_code: isv.business-failed:628145006） | 联系行业运营完成抖店会员数据升级到会员通体系 |
| `50002` | 业务处理失败 / 用户是品牌会员，必须使用品牌唯一身份的UnionId来更新（sub_code: isv.business-failed:628145036） | 当前是批量接口，针对品牌会员的那一行更新请传入unionId |
| `50002` | 业务处理失败 / 请求超时，请稍后重试（sub_code: isv.business-failed:628004002） | 请求超时，请稍后重试 |
| `50002` | 业务处理失败 / 会员已经在平台设置生日，不允许商家外部系统更新（sub_code: isv.business-failed:628145045） | 会员已经在平台设置生日，不允许商家外部系统更新 |
| `50002` | 业务处理失败 / 【抖店会员体系升级会员通体系】会员数据传输中，请勿更新会员数据，等待升级完成。如有疑问，请联系商家IT或者服务商技术同学咨询（sub_code: isv.business-failed:628143000） | 请等待【抖店会员体系升级会员】升级完成 |
| `50002` | 业务处理失败 / UnionId非法，无法正常解析（sub_code: isv.business-failed:628145021） | 请检查传入的UnionId和token店铺ID是否有关联？确认UnionId是否合法？ |
| `50002` | 业务处理失败 / 请求的店铺非品牌店铺（sub_code: isv.business-failed:628145007） | 请检查传入的token归属店铺ID是否是品牌店铺 |
| `50002` | 业务处理失败 / 更新用户信息失败（sub_code: isv.business-failed:628145047） | 内部操作失败，请稍后再试 |
| `50002` | 业务处理失败 / 未授权商家禁止使用会员清退功能（sub_code: isv.business-failed:628145050） | 如需要使用会员注销功能，请联系会员通运营同学申请权限 |
| `50002` | 业务处理失败 / 用户不满足注销的无活跃要求（sub_code: isv.business-failed:628145051） | 用户不满足注销的无活跃要求，禁止注销该用户 |

## 响应示例

成功：

```json
{
  "data": {
    "batch_update_response_info": [
      {
        "err_code": "0",
        "err_msg": "网络错误，请稍后再试",
        "extend": "{}",
        "open_id": "cb7bf7efa6d652046abd2f7d84ee18c1",
        "success": "true",
        "union_id": "#YOUR_SECRET_KEY"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:628145000",
  "sub_msg": "网络错误，请稍后再试~"
}
```

## 备注
