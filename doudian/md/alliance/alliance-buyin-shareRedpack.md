# buyin.shareRedpack

> 抖客红包转链

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.shareRedpack` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/shareRedpack` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2547 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `redpack_id` | body | string | 是 | 红包批次ID | `123456` |
| `pid` | body | string | 是 | 抖客PID | `dy_1234_123_123` |
| `external_info` | body | string | 否 | 自定义字段，只允许 数字、字母和_，限制长度为40 | `123_456` |
| `need_qr_code` | body | boolean | 否 | 是否需要二维码(获取二维码将增加响应耗时，推荐false) | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/shareRedpack?app_key=your_appkey_here&method=buyin.shareRedpack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 当前抖客未开通直播间分销业务权限（sub_code: isv.business-failed:4113） | 当前抖客未开通直播间分销业务权限 |
| `40004` | 非法的参数 / 参数校验失败：无效 PID（sub_code: isv.parameter-invalid:4102） | 参数校验失败：无效 PID |
| `40004` | 非法的参数 / 红包不存在（sub_code: isv.parameter-invalid:4118） | 红包不存在 |
| `40004` | 非法的参数 / 非抖客渠道红包（sub_code: isv.parameter-invalid:4299） | 非抖客渠道红包 |
| `40004` | 非法的参数 / 红包不是生效状态或已领完（sub_code: isv.parameter-invalid:4120） | 红包不是生效状态或已领完 |
| `40004` | 非法的参数 / 红包未到或已过领取时间，不可转链（sub_code: isv.parameter-invalid:4300） | 红包未到或已过领取时间，不可转链 |
| `40004` | 非法的参数 / 红包参数校验失败（sub_code: isv.parameter-invalid:4298） | 红包参数校验失败 |
| `40004` | 非法的参数 / 无效 external_info（sub_code: isv.parameter-invalid:4101） | 参数校验失败：无效 external_info |
| `40004` | 非法的参数 / 抖客红包不支持自营（sub_code: isv.parameter-invalid:4116） | 抖客红包不支持自营 |
| `50002` | 业务处理失败 / 达人无抖客红包权限（sub_code: isv.business-failed:4117） | 达人无抖客红包权限 |
| `40004` | 非法的参数 / 红包参数非法（sub_code: isv.parameter-invalid:4119） | 红包参数非法 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_code": "isv.parameter-invalid:4097",
  "sub_msg": "参数校验失败"
}
```

## 备注
