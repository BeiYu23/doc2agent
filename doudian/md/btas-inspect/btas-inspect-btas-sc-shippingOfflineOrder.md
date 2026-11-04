# btas.sc.shippingOfflineOrder

> 质检机构在收到实物质检商品质检完成，并且同步到平台后，进行发货。 此时，如果订单已经已经取消就是发往商家（如果商家是自提则接口会报错）；如果订单未取消，则发往消费者。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.btas-inspect.btas.sc.shippingOfflineOrder` |
| 中文名 | 质检机构在收到实物质检商品质检完成 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/sc/shippingOfflineOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/2948 |
| 更新日期 | `2023-02-10` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `041513133` |
| `sc_id` | body | number | 是 | 质检机构ID | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpInboundCancel?app_key=your_appkey_here&method=yunc.erpInboundCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `seller_send_type` | string | 商家送检方式。1，邮寄。2：面交 | `1` |
| `logistics_num` | string | 快递单号。面交没有这个字段 | `SF2342342` |
| `logistics_name_cn` | string | 快递公司名称 | `顺丰` |
| `logistics_name_en` | string | 快递公司英文名称 | `shunfeng` |
| `receiver_type` | string | 收货人类型，-1-未知;0-买家收货;1-卖家收货。-1的情况是质检站点在btas系统中，修改了发货信息，但是实际上发给谁，系统并不清楚 | `1` |
| `order_code` | string | 发货的orderCode | `02131231` |
| `logistics_pdf_file` | string | 发货物流PDF文件 | `base64://s234234dsfadfaf` |
| `cancel_status` | string | 订单取消状态。0-未取消；1-申请取消；2-订单已经取消；4-退款&订单已取消；6-退货退款&订单已取消 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -2:电子面单订购关系不存在;（sub_code: isv.business-failed:-2） | -2:电子面单订购关系不存在; |
| `50002` | 业务处理失败 / -1:运单不满足发货条件（sub_code: isv.business-failed:-1） | -1:运单不满足发货条件 |

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
  "sub_code": "isv.business-failed:-2",
  "sub_msg": "-2:电子面单订购关系不存在;"
}
```

## 备注
