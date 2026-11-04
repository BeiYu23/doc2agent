# mini.activity.edit

> 编辑小程序专属价活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.activity.edit` |
| 中文名 | 编辑小程序专属价活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/edit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/4956 |
| 更新日期 | `2023-10-13` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 是 | 活动id | `7279756826818658604` |
| `activity_start_time` | body | number | 否 | 活动开始时间 | `1695015497` |
| `activity_end_time` | body | number | 否 | 活动结束时间 | `1695015497` |
| `user_buy_limit` | body | number | 否 | 用户限购数量 | `10` |
| `activity_name` | body | string | 否 | 活动名称 | `新品发售专属价` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/activity/edit?app_key=your_appkey_here&method=mini.activity.edit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:606010000） | 请检查入参 |
| `50002` | 业务处理失败 / 活动已失效，不允许编辑（sub_code: isv.business-failed:605030008） | 请新建活动 |
| `50002` | 业务处理失败 / 上线中的活动不允许直接编辑（sub_code: isv.business-failed:605030018） | 请先下线活动 |
| `50002` | 业务处理失败 / 您的操作过于频繁，请稍后重试（sub_code: isv.business-failed:606000105） | 您的操作过于频繁，请稍后重试 |
| `50002` | 业务处理失败 / 活动不存在，请稍后重试（sub_code: isv.business-failed:605030006） | 活动不存在，请稍后重试 |
| `50002` | 业务处理失败 / 非法的操作（sub_code: isv.business-failed:606000106） | 请参考错误描述调整请求入参 |

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
  "sub_code": "isv.parameter-invalid:606010000",
  "sub_msg": "非法的参数"
}
```

## 备注
