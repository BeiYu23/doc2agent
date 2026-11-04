# mini.activity.create

> 创建小程序专属价活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.activity.create` |
| 中文名 | 创建小程序专属价活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/4958 |
| 更新日期 | `2023-10-13` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_name` | body | string | 是 | 活动名称 | `新品专享价` |
| `product_id` | body | number | 是 | 活动商品id | `3639483739320549069` |
| `activity_start_time` | body | number | 是 | 活动开始时间 | `1695015497` |
| `activity_end_time` | body | number | 是 | 活动结束时间 | `1695015497` |
| `user_buy_limit` | body | number | 否 | 用户限购数量 | `10` |
| `online_directly` | body | boolean | 否 | 是否直接上线活动 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/activity/create?app_key=your_appkey_here&method=mini.activity.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | string | 活动id | `7279756826818658604` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:606010000） | 请检查入参 |
| `20000` | 系统错误 / 并发错误（sub_code: isp.service-error:606000105） | 您的操作过于频繁，请稍后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:606000103） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 活动名称已存在（sub_code: isv.business-failed:605030003） | 请修改活动名称 |
| `50002` | 业务处理失败 / 商品已经被绑定到其他活动上（sub_code: isv.business-failed:605030004） | 请检查商品 |
| `50002` | 业务处理失败 / 该商品非小程序专属价商品（sub_code: isv.business-failed:605030002） | 请检查商品标题是否以【专属价】开头 |
| `50002` | 业务处理失败 / 商品状态非已下架（sub_code: isv.business-failed:605030005） | 创建活动时绑定的商品必须先下架 |
| `50002` | 业务处理失败 / 商品必须设置为不可见（sub_code: isv.business-failed:605030017） | 请到商家后台【商品管理】->【批量设置】设置商品为不可见 |
| `50002` | 业务处理失败 / 商品不存在（sub_code: isv.business-failed:605030000） | 商品不存在 |
| `50002` | 业务处理失败 / 商品必须是普通实物商品（sub_code: isv.business-failed:606010025） | 商品必须是普通实物商品 |

## 响应示例

成功：

```json
{
  "data": {
    "activity_id": "7279756826818658604"
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
  "sub_code": "isv.parameter-invalid:606010000",
  "sub_msg": "参数错误"
}
```

## 备注
