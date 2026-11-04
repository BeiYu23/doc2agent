# mini.activity.userRegister

> 专享价活动注册

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.activity.userRegister` |
| 中文名 | 专享价活动注册 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/activity/userRegister` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6767 |
| 更新日期 | `2024-08-20` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 否 | 活动id | `7390039288967987465` |
| `buy_limit` | body | mixed | 否 | 限购数量 | `10` |
| `register_token` | body | string | 否 | 预注册接口出参返回的token | `YOUR_SECRET_KEY` |
| `dy_open_id` | body | string | 否 | dy_open_id | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=mini.activity.userRegister&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `user_activity_right_no` | string | 用户权益单号 | `7390039288967987465` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请检查必填参数（sub_code: isv.parameter-invalid:606010000） | 请检查必填参数 |
| `50002` | 业务处理失败 / 您的操作过于频繁，请稍后重试（sub_code: isv.business-failed:606000105） | 您的操作过于频繁，请稍后重试 |
| `40004` | 非法的参数 / 应用不存在（sub_code: isv.parameter-invalid:605030012） | 应用不存在 |
| `40004` | 非法的参数 / 用户不存在（sub_code: isv.parameter-invalid:605030023） | 用户不存在 |
| `50002` | 业务处理失败 / 活动暂未上线（sub_code: isv.business-failed:605030022） | 活动暂未上线 |
| `50002` | 业务处理失败 / 活动暂未开始（sub_code: isv.business-failed:605030014） | 活动暂未开始 |
| `50002` | 业务处理失败 / 系统错误，请稍后重试（sub_code: isv.business-failed:605030008） | 系统错误，请稍后重试 |
| `20000` | 系统错误 / 系统错误，请稍后重试（sub_code: isp.service-error:606000103） | 系统错误，请稍后重试 |
| `50002` | 业务处理失败 / 您已注册过该活动，请不要重复注册（sub_code: isv.business-failed:605030010） | 您已注册过该活动，请不要重复注册 |
| `50002` | 业务处理失败 / 用户限购数量不能为空（sub_code: isv.business-failed:605030011） | 用户限购数量不能为空 |
| `50002` | 业务处理失败 / 活动不存在（sub_code: isv.business-failed:605030006） | 活动不存在 |
| `50002` | 业务处理失败 / 暂无购买资格（sub_code: isv.business-failed:606010026） | 暂无购买资格 |
| `50002` | 业务处理失败 / 当前应用无当前活动的操作权限（sub_code: isv.business-failed:606000106） | 当前应用无当前活动的操作权限 |
| `50002` | 业务处理失败 / 活动已失效（sub_code: isv.business-failed:605030009） | 活动已失效 |

## 响应示例

成功：

```json
{
  "data": {
    "user_activity_right_no": "7390039288967987465"
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
