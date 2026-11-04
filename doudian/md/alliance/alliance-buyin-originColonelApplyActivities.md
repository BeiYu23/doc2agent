# 团长报名二级团长活动

> buyin.originColonelApplyActivities — 团长报名二级团长活动

| 元信息 | 值 |
| --- | --- |
| 中文名 | 团长报名二级团长活动 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-originColonelApplyActivities` |
| 接口 ID | `doudian.alliance.buyin.originColonelApplyActivities` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/originColonelApplyActivities` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1672 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V7.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 是 | 活动ID | `54321` |
| `phone_number` | body | string | 是 | 联系电话 | `15671111111` |
| `products` | body | array | 是 | 商品列表 | `` |
| `  └ product_id` | body | mixed | 是 | 商品ID | `123687541` |
| `  └ origin_activity_id` | body | mixed | 是 | 原始活动ID（托管商品传0） | `54321` |
| `  └ promotion_end_time` | body | string | 否 | 商品推广结束时间 | `2022-01-10` |
| `service_ratio` | body | string | 否 | 招商服务费率。 服务费率+佣金率小于90（必须为两位小数） | `10.00` |
| `cos_type` | body | mixed | 否 | 佣金类型 0:固定佣金 1:双佣金 | `1` |
| `ad_service_ratio` | body | string | 否 | 双佣金投放期服务费率（小数） | `5.00` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/originColonelApplyActivities?app_key=your_appkey_here&method=buyin.originColonelApplyActivities&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 操作的商品数量 | `20` |
| `result` | array | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务处理失败，请查看具体错误信息（sub_code: isv.business-failed:110110） | 业务处理失败，请查看具体错误信息 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:500） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 小数服务费率不合法，必须为两位小数（sub_code: isv.business-failed:8192） | 小数服务费率不合法，必须为两位小数 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "error_code": "0",
        "error_msg": "success",
        "is_success": "true",
        "product_id": "123123123123"
      }
    ],
    "total": "20"
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
  "sub_code": "isv.business-failed:110110",
  "sub_msg": "业务处理失败，请查看具体错误信息"
}
```

## 备注
