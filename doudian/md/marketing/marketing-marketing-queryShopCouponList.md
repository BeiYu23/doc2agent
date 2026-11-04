# marketing.queryShopCouponList

> 查询店铺优惠券信息，与商家工作台优惠券管理模块功能一致

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.marketing.marketing.queryShopCouponList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/marketing/queryShopCouponList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1361/4257 |
| 更新日期 | `2023-08-04` |

## 接口说明

- 文档书: 营销管理API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `coupon_type` | body | number | 否 | 优惠券类型。 0表示全部。 1：会员开卡礼；3：商品优惠券；4：店铺粉丝券；5：达人粉丝券；6：店铺新人券；7：全店通用券；8：客服专享卷；9：自有渠道券；12：团长活动券；13：达人专属券；15：订单商品复购券；16：直播投流券；20：无忧服务客服券；23：电商品牌广告券 | `0` |
| `content_type` | body | number | 否 | 优惠内容。 0表示全部。 1：店铺满减券；2：店铺直减券；3：店铺折扣券；11：指定商品满减券；12：指定商品直减券；13：指定商品折扣券； | `0` |
| `status` | body | number | 否 | 优惠券状态。 0表示全部。 1: 未生效，2：生效中。3：已过期，4：已作废 | `0` |
| `min_start_apply_time` | body | number | 否 | 领取时间范围，最小领取时间 | `2023-07-01 00:00:00` |
| `max_start_apply_time` | body | number | 否 | 领取时间范围，最大领取时间 | `2023-08-01 00:00:00` |
| `page_no` | body | number | 是 | 分页参数，页数；从0开始 | `0` |
| `page_size` | body | number | 是 | 分页参数，每页大小，最大20； | `10` |
| `coupon_id` | body | string | 否 | 优惠券ID，用于定向查询 | `7261824374827712828` |
| `conpon_name` | body | string | 否 | 优惠券名称，用于模糊查询 | `店铺券` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=crossborder.link.inboundBill.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `coupon_list` | array | 优惠券列表 | `` |
| `total` | number | 总量 | `1023` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 店铺优惠券查询异常，缺少分页参数（sub_code: isv.parameter-invalid:605012024） | 请填写正确的分页参数 |
| `40004` | 非法的参数 / 店铺优惠券查询异常，分页参数不合法（sub_code: isv.parameter-invalid:605012025） | 请填写正确的分页参数，PageNo <= 20 |
| `40004` | 非法的参数 / 店铺优惠券查询异常，时间格式不正确（sub_code: isv.parameter-invalid:605012026） | max_start_apply_time不能早于min_start_apply_time |
| `20000` | 系统错误 / 店铺优惠券查询异常，请稍后重试（sub_code: isp.service-error:605012000） | 店铺优惠券查询异常，请稍后重试 |

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
  "sub_code": "isv.parameter-invalid:605012024",
  "sub_msg": "店铺优惠券查询异常，缺少分页参数"
}
```

## 备注
