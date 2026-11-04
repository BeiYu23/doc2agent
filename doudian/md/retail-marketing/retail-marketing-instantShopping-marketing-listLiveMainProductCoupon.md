# instantShopping.marketing.listLiveMainProductCoupon

> 批量查询直播主品券活动

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.listLiveMainProductCoupon` |
| 中文名 | 批量查询直播主品券活动 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7253 |
| 更新日期 | `2025-02-10` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 默认1 | `1` |
| `status` | body | mixed | 否 | 活动状态 | `90` |
| `activity_sub_type` | body | mixed | 否 | 优惠类型 | `301` |
| `activity_id_list` | body | array | 否 | 活动ID列表 | `["1111"]` |
| `size` | body | mixed | 是 | 默认20 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.marketing.listLiveMainProductCoupon&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回信息 | `` |
| `total` | mixed | 总数 | `10` |

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
        "activity_id": "1111",
        "activity_status": "90",
        "activity_sub_type": "301",
        "activity_title": "活动A",
        "activity_type": "30",
        "coupon_base_info": {
          "activity_end_time": "1738166399",
          "activity_start_time": "1738166399",
          "apply_end_time": "1738166399",
          "apply_start_time": "1738166399",
          "apply_way": "1",
          "biz_type": "2",
          "credit": "1000",
          "discount": "20",
          "max_apply_times": "10",
          "threshold": "2000",
          "total_amount": "10",
          "valid_period": "172800"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
