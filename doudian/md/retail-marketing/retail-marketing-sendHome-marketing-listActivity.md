# 查询营销活动列表

> sendHome.marketing.listActivity — 查询营销活动列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询营销活动列表 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-sendHome-marketing-listActivity` |
| 接口 ID | `doudian.retail-marketing.sendHome.marketing.listActivity` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6809 |
| 更新日期 | `2024-08-27` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id_list` | body | array | 否 | 活动ID列表 | `{123}` |
| `page` | body | mixed | 否 | 默认1 | `1` |
| `size` | body | mixed | 否 | 默认20 | `20` |
| `status` | body | mixed | 否 | 活动状态 Init = 10,       // 创建中 Fail = 20,       // 创建失败 Invaliding = 30, // 失效中 Invalid = 40,    // 失效 Delete = 50,     // 已删除 Success = 90,    // 创建成功 | `10` |
| `activity_type` | body | mixed | 否 | 活动类型 TimeLimitedBuy = 10,    // 限时限量购 FullDiscount = 40,      // 满减 | `10` |
| `activity_sub_type` | body | mixed | 否 | 优惠类型 SecKill = 101,                   // 限时秒杀 PriceOff = 102,                  // 普通降价促销  NthPriceForDiscount = 401,       // 满N元优惠 NthPieceForDiscount = 402,       // 满N件优惠 | `101` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sendHome.marketing.listActivity&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 活动列表 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "activity_base_info": {
          "activity_end_time": "1723451737",
          "activity_id": "123",
          "activity_start_time": "1723451737",
          "activity_status": "10",
          "activity_sub_type": "401",
          "activity_title": "\"月末满减活动\"",
          "activity_type": "40"
        },
        "activity_detail_info": {
          "full_discount_info": {
            "condition_type": "1",
            "discount_rules": [
              {
                "condition_value": "10",
                "discount_value": "1"
              }
            ],
            "discount_type": "1"
          }
        }
      }
    ],
    "total": "10"
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
