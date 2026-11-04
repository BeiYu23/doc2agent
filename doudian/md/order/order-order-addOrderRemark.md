# order.addOrderRemark

> 为商家提供订单备注接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.addOrderRemark` |
| 中文名 | 为商家提供订单备注 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/addOrderRemark` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/568 |
| 更新日期 | `2024-08-15` |

## 接口说明

- 文档书: 订单API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 店铺订单ID。 | `6496679971677798670` |
| `remark` | body | string | 是 | 备注内容，必填选项。如果不填会导致订单的备注被空值覆盖，最大不得超过500个字符。 | `这是具体的备注内容` |
| `is_add_star` | body | string | 否 | 是否加旗标，不填则默认为false，不会修改旗帜颜色。 is_add_star=true，需要加旗帜或者覆盖原来的旗帜颜色；is_add_star=false，不添加旗帜，不会覆盖原来的旗帜颜色。 | `true` |
| `star` | body | string | 否 | 标星等级，范围0～5 0为灰色旗标，5为红色旗标，数字越大颜色越深 0灰 1紫 2青 3绿 4橙 5红 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/addOrderRemark?app_key=your_appkey_here&method=order.addOrderRemark&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 50001:orderId参数不合法，建议根据文档检查传入数据（sub_code: isv.parameter-invalid:50001） | 参数错误，检查参数 |
| `20000` | 系统错误 / 20001:系统繁忙，请稍后重试（sub_code: isp.service-error:20001） | 重试 |
| `40004` | 非法的参数 / 50002:参数不合法，建议根据文档检查传入数据（sub_code: isv.parameter-invalid:50002） | 参数错误，检查参数 |
| `40004` | 非法的参数 / 50051:备注不规范，建议检查备注文案（sub_code: isv.parameter-invalid:50051） | 备注不规范，检查参数 |
| `40004` | 非法的参数 / 20002:orderId不存在，请检查订单号（sub_code: isv.parameter-invalid:20002） | 订单号不存在，检查参数 |
| `20000` | 系统错误 / 8888:系统繁忙，请稍后重试（sub_code: isp.service-error:8888） | 重试 |
| `50002` | 业务处理失败 / 50056:订单备注内容超过规定字数（sub_code: isv.business-failed:50056） | 订单备注内容超过规定字数 |

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
  "sub_code": "isv.parameter-invalid:50001",
  "sub_msg": "50001:orderId参数不合法，建议根据文档检查传入数据"
}
```

## 备注
