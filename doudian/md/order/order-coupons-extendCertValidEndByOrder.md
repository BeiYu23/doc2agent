# 三方卡券延期

> coupons.extendCertValidEndByOrder — 三方卡券延期

| 元信息 | 值 |
| --- | --- |
| 中文名 | 三方卡券延期 |
| 文档地址 | `/docs/doudian/order/order-coupons-extendCertValidEndByOrder` |
| 接口 ID | `doudian.order.coupons.extendCertValidEndByOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/extendCertValidEndByOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1730 |
| 更新日期 | `2022-03-22` |

## 接口说明

- 文档书: 订单API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 商品单id | `4910456132661405505` |
| `batch_no` | body | string | 是 | 请求唯一编号 | `batch000001` |
| `extend_time` | body | number | 是 | 延期时间 | `1647399907` |
| `reason` | body | string | 是 | 延期原因。1-疫情原因，2-商家缺货，100-其他原因 | `1` |
| `op` | body | object | 否 | 操作人信息 | `` |
| `  └ platform` | body | string | 否 | 操作人平台 | `1` |
| `  └ op_uid` | body | number | 否 | 操作人id | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/extendCertValidEndByOrder?app_key=your_appkey_here&method=coupons.extendCertValidEndByOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_status` | string | 是否成功 | `SUCCESS` |
| `ret_code` | string | 错误码 | `010027` |
| `ret_message` | string | 错误描述 | `只能延长卡券有效期，请检查` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 延期失败（sub_code: isv.business-failed:010027） | 延期失败 |
| `40002` | 缺少必选参数 / extendTime不能为空（sub_code: isv.missing-parameter:000002） | 补充必要参数 |
| `40004` | 非法的参数 / 订单不存在（sub_code: isv.parameter-invalid:010006） | 修改参数 |

## 响应示例

成功：

```json
{
  "data": {
    "ret_code": "010027",
    "ret_message": "只能延长卡券有效期，请检查",
    "ret_status": "SUCCESS"
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
  "sub_code": "isv.business-failed:010027",
  "sub_msg": "延期失败"
}
```

## 备注
