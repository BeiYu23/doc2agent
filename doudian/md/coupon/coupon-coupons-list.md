# coupons.list

> 平台卡券和三方卡券的status枚举不一样。平台卡券状态码status的枚举是1:未使用，2:已使用，3：已失效，查询时需入参cert_type=1；
商家(三方)卡券状态码status的枚举是1 //未激活（表示初始状态）； 2 //未使用； 3 //已

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.coupon.coupons.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/369 |
| 更新日期 | `2024-03-21` |

## 接口说明

- 文档书: 卡券API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 子订单id | `123` |
| `cert_no` | body | string | 否 | 卡号券码 | `卡券id` |
| `cert_type` | body | number | 否 | 卡券类型（0-三方卡券；1-平台卡券） | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=yunc.wms.cargo.single.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 000002:参数错误（sub_code: isv.business-failed:2） | 校验入参是否正确 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2",
  "sub_msg": "000002:参数错误"
}
```

## 备注
