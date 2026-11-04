# marketing.checkCouponApplied

> 查询用户已领取优惠券核销数量

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.checkCouponApplied` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/checkCouponApplied` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/4258 |
| 更新日期 | `2023-08-04` |

## 接口说明

- 文档书: 营销管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_id` | body | string | 是 | 优惠券ID | `7261824374827712828` |
| `doudian_open_id` | body | number | 是 | 抖店用户open_id | `1@#YOUR_SECRET_KEY` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/marketing/checkCouponApplied?app_key=your_appkey_here&method=marketing.checkCouponApplied&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `used_count` | number | 这个活动优惠id下，用户已使用（已核销）优惠券数量；该统计维度仅包含只包含已领取且已使用。如用户未领取或已领取未使用均不统计； | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:605012000） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 优惠券不存在，请填写正确的券ID（sub_code: isv.parameter-invalid:605012020） | 请填写正确的券ID |

## 响应示例

成功：

```json
{
  "data": {
    "used_count": "1"
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
  "sub_code": "isp.service-error:605012000",
  "sub_msg": "系统异常，请稍后重试"
}
```

## 备注
