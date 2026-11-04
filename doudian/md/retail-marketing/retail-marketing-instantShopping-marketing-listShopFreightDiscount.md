# instantShopping.marketing.listShopFreightDiscount

> 查询配送费满减活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.listShopFreightDiscount` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7550 |
| 更新日期 | `2025-07-03` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 翻页页码 | `1` |
| `size` | body | mixed | 是 | 每页条数 | `20` |
| `activity_type` | body | mixed | 否 | 活动类型，50:配送费营销 | `50` |
| `activity_sub_type` | body | mixed | 否 | 活动子类型，502:配送费满减 | `502` |
| `status` | body | mixed | 否 | 活动状态 | `90` |
| `activity_id_list` | body | array | 否 | 活动ID列表 | `[123,124]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.marketing.listShopFreightDiscount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 查询结果 | `` |
| `total` | mixed | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "activity_base_info": {
          "activity_end_time": "1711266959",
          "activity_start_time": "1711265959",
          "day_time_range": [
            {
              "end_time": "86399",
              "start_time": "0"
            }
          ],
          "discount_rules": [
            {
              "condition_value": "1000",
              "discount_value": "100"
            }
          ],
          "is_free_freight": "false",
          "limit_week": "[1,2,3,4,5,6,7]",
          "subsidy_apply_way": "ALL_ACTIVITY_TIME"
        },
        "activity_id": "123",
        "activity_status": "90",
        "activity_sub_type": "502",
        "activity_title": "测试活动",
        "activity_type": "50"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
