# 店铺会员绑定渠道关系创建

> buyin.shopPidMemberCreate — 店铺会员绑定渠道关系创建

| 元信息 | 值 |
| --- | --- |
| 中文名 | 店铺会员绑定渠道关系创建 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-shopPidMemberCreate` |
| 接口 ID | `doudian.alliance.buyin.shopPidMemberCreate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/shopPidMemberCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1493 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pid` | body | string | 是 | 人店一体达人PID | `dy_123_345_456` |
| `member_available_time` | body | mixed | 是 | 会员绑定有效天数，至少30天 | `365` |
| `external_info` | body | string | 否 | 自定义字段，只允许 数字、字母和_，限制长度为40 | `external_info_test` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/shopPidMemberCreate?app_key=your_appkey_here&method=buyin.shopPidMemberCreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `qrcode` | string | 入会二维码 | `https://p26.douyinpic.com/img/aweme-qrcode/eZlDuG70339820345906863~c5_360x360.webp?from=1723184` |
| `member_join_url` | string | 入会跳转URL | `https://aweme.snssdk.com/ecom_member/facade_douyin/v1/join_member_link/?sec_shop_uid=MS4wLjABAAAAgRxF3bIh9bhDhDjEeQBkUQpyn-zXyLjZf6bt5y8UW-0Kc8yuRezI&page_from=dy_lm&pid=dy_123_345_456&pid_extra=eyJtZW1iZXJfYXZxhYmxlX3RpbWUiOjfQ&pid_sign=b16b975bab337c552651e35ff97c7b` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 检查参数是否正确 |
| `40004` | 非法的参数 / 会员绑定有效期必须大于30天（sub_code: isv.parameter-invalid:4103） | 检查参数是否正确 |
| `50002` | 业务处理失败 / 当前机构或商家尚未开通分销权限（sub_code: isv.business-failed:4105） | 当前机构或商家尚未开通分销权限 |
| `50002` | 业务处理失败 / 当前商家暂未开通会员（sub_code: isv.business-failed:4106） | 当前商家暂未开通会员 |
| `50002` | 业务处理失败 / 未知错误（sub_code: isv.business-failed:255） | 未知错误 |
| `50002` | 业务处理失败 / 当前商家未绑定人店一体官方账号（sub_code: isv.business-failed:4107） | 当前商家未绑定人店一体官方账号 |
| `40004` | 非法的参数 / 当前pid非此店铺绑定官方达人所创建（sub_code: isv.parameter-invalid:4108） | 当前pid非此店铺绑定官方达人所创建 |
| `40004` | 非法的参数 / 无效 PID（sub_code: isv.parameter-invalid:4102） | 参数校验失败：无效 PID |
| `40004` | 非法的参数 / 无效 external_info（sub_code: isv.parameter-invalid:4101） | 参数校验失败：无效 external_info |

## 响应示例

成功：

```json
{
  "data": {
    "member_join_url": "https://aweme.snssdk.com/ecom_member/facade_douyin/v1/join_member_link/?sec_shop_uid=MS4wLjABAAAAgRxF3bIh9bhDhDjEeQBkUQpyn-zXyLjZf6bt5y8UW-0Kc8yuRezI&page_from=dy_lm&pid=dy_123_345_456&pid_extra=eyJtZW1iZXJfYXZxhYmxlX3RpbWUiOjfQ&pid_sign=b16b975bab337c552651e35ff97c7b",
    "qrcode": "https://p26.douyinpic.com/img/aweme-qrcode/eZlDuG70339820345906863~c5_360x360.webp?from=1723184"
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
