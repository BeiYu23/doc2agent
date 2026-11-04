# 创建满减营销活动

> sendHome.marketing.creatFullDiscountActivity — 创建满减营销活动，支持创建：满x元减x元，满x件减x元，满x件打x折

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建满减营销活动 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-sendHome-marketing-creatFullDiscountActivity` |
| 接口 ID | `doudian.retail-marketing.sendHome.marketing.creatFullDiscountActivity` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6812 |
| 更新日期 | `2024-08-29` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_title` | body | string | 否 | 活动标题，最大长度25 | `"月末满减活动"` |
| `activity_start_time` | body | number | 否 | 秒级时间戳，活动开始时间，不可以早于当天00:00 | `1723451737` |
| `activity_end_time` | body | number | 否 | 秒级时间戳，活动结束时间，活动持续时长不可以超过90天 | `1723451737` |
| `full_discount_info` | body | object | 否 | 满减活动信息 | `` |
| `  └ condition_type` | body | string | 否 | Price = 1, // 满元 Amount = 2, // 满件 | `1` |
| `  └ discount_type` | body | string | 否 | ReducePrice = 1, // 满减 Discount = 2, // 打折 | `1` |
| `  └ discount_rules` | body | array | 否 | 阶梯满减规则，后面的阶梯需比前面的折扣力度更大 如创建满x元减x元活动  {   {1000, 100},   {2000, 200} } 代表满10元减1元，满20元减2元（第二个满减折扣力度大于第一个） 如果为满x元优惠，最多设置5条阶梯满减规则 如果为满x件优惠，最多设置3条阶梯满减规则 | `` |
| `    └ discount_value` | body | string | 否 | 满减折扣，代表减x元或者打x折，只允许输入整数 减x元输入单位为：分 打x折输入单位为：0.1折 | `10` |
| `    └ condition_value` | body | string | 否 | 满减条件，代表满x元或者满x件，只允许输入整数 满x元输入单位为：分 满x件输入单位为：件 | `2` |
| `request_id` | body | string | 否 | 幂等id，不能为空且不超过100个字符（RequestId做幂等） | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/template/search?app_key=your_appkey_here&method=sms.template.search&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `activity_id` | string | 满减活动id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |

## 响应示例

成功：

```json
{
  "data": {
    "template_search_list": [
      {
        "channel_type": "CN_NTC",
        "sms_account": "1234",
        "template_content": "您购买的商品已重新发出，${name}快递运单号：${number}，关注“XXX”公众号刷新订单获取最新物流信息哦~给您造成不便敬请谅解。",
        "template_id": "43534",
        "template_name": "618大促"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
