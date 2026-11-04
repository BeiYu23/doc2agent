# 用户注册活动

> mini.activity.register — 用户注册活动

| 元信息 | 值 |
| --- | --- |
| 中文名 | 用户注册活动 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-activity-register` |
| 接口 ID | `doudian.miniapp.mini.activity.register` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/register` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/4957 |
| 更新日期 | `2024-01-29` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 是 | 活动id | `7279756826818658604` |
| `buy_limit` | body | mixed | 否 | 限购数量 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.activity.register&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `user_activity_right_no` | string | 用户权益单号 | `用户权益单号` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请检查必填参数（sub_code: isv.parameter-invalid:606010000） | 请检查必填参数 |
| `50002` | 业务处理失败 / 您的操作过于频繁，请稍后重试（sub_code: isv.business-failed:606000105） | 请降低请求频率 |
| `40004` | 非法的参数 / 应用不存在（sub_code: isv.parameter-invalid:605030012） | 请检查当前应用是否绑定了对应的小程序 |
| `40004` | 非法的参数 / 用户不存在（sub_code: isv.parameter-invalid:605030023） | 请检查用户是否合法 |
| `50002` | 业务处理失败 / 活动暂未上线（sub_code: isv.business-failed:605030022） | 请先上线活动 |
| `50002` | 业务处理失败 / 活动暂未开始（sub_code: isv.business-failed:605030014） | 请等待活动开始后参与 |
| `50002` | 业务处理失败 / 活动已失效（sub_code: isv.business-failed:605030008） | 活动已失效 |
| `20000` | 系统错误 / 系统错误，请稍后重试（sub_code: isp.service-error:606000103） | 系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 您已注册过该活动，请不要重复注册（sub_code: isv.business-failed:605030010） | 您已注册过该活动，请不要重复注册 |
| `50002` | 业务处理失败 / 用户限购数量不能为空（sub_code: isv.business-failed:605030011） | 用户限购数量不能为空 |
| `50002` | 业务处理失败 / 活动不存在（sub_code: isv.business-failed:605030006） | 活动不存在 |
| `50002` | 业务处理失败 / 暂无购买资格（sub_code: isv.business-failed:606010026） | 暂无购买资格 |
| `50002` | 业务处理失败 / 当前应用无当前活动的操作权限（sub_code: isv.business-failed:606000106） | 当前应用无当前活动的操作权限 |
| `50002` | 业务处理失败 / 活动已失效（sub_code: isv.business-failed:605030009） | 活动商品解绑后，活动失效 |

## 响应示例

成功：

```json
{
  "data": {
    "user_activity_right_no": "用户权益单号"
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
  "sub_msg": "请检查必填参数"
}
```

## 备注
