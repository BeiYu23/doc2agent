# mini.luxOrderMerchantConfirm

> 奢品订单商家确认接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.mini.luxOrderMerchantConfirm` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/luxOrderMerchantConfirm` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/8392 |
| 更新日期 | `2026-07-06` |

## 接口说明

- 文档书: 飞鸽API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sku_order_id` | body | mixed | 是 | sku订单id | `6954158301937669XXX` |
| `shop_order_id` | body | mixed | 是 | 店铺订单id | `6954158301937669YYY` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/luxOrderMerchantConfirm?app_key=your_appkey_here&method=mini.luxOrderMerchantConfirm&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 成功为true，否则为false | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 请求参数问题（sub_code: isv.missing-parameter:28007004） | 请按要求传递所有必填参数 |
| `40004` | 非法的参数 / 订单查询失败（sub_code: isv.parameter-invalid:28007006） | 请咨询技术支持检查订单详细信息 |
| `50002` | 业务处理失败 / 不合法的业务处理，有很多可能性，都是不符合奢品定制订单确认的情况，根据返回消息来确认具体的错误原因（sub_code: isv.business-failed:28007005） | 根据返回消息进行确认 |
| `60000` | 触发限流，请稍后重试 / 拒绝请求（sub_code: isp.traffic-limited:28007001） | qps问题或锁竞争问题，降低请求频次 |
| `20000` | 系统错误 / 系统组件相关错误（sub_code: isp.service-error:28001005） | 提供logId咨询技术支持 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:28007004",
  "sub_msg": "请求参数问题"
}
```

## 备注
