# supplyChain.queryReturnOrderList

> 根据筛选条件批量查询售后单列表，单次最多返回100个

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.queryReturnOrderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryReturnOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/4034 |
| 更新日期 | `2026-03-05` |

## 接口说明

- 文档书: 供销平台API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_order_no` | body | string | 否 | 售后单号 | `GSH123123123` |
| `channel_trade_order_no` | body | string | 否 | 供货单号 | `CT12312312312` |
| `standard_order_status` | body | string | 否 | 订单标准状态；1-待抖店商家同意退款；2-待供应商同意退款；3-待买家退货；4-买家已退货，待供应商确认收货；5-退款中；6-退款成功；7-售后仲裁中；8-待供应商同意退货申请；9-待商家/分销商退货；11-待平台审核退款；12-待平台审核退货申请；13-已退货，待平台审核退款；20-售后取消；21-售后关闭；22-售后拒绝；23-售后异常 | `1` |
| `create_date_begin` | body | number | 否 | 创建时间开始，单位为秒（查询范围包含开始值） | `1626856525` |
| `create_date_end` | body | number | 否 | 创建结束开始，单位为秒（查询范围包含开始值） | `1626856525` |
| `page` | body | string | 是 | 页数，从1开始 | `1` |
| `size` | body | string | 是 | 每页数量，最多100个 | `50` |
| `order_type` | body | string | 否 | 售后类型；1-退货退款，3-退款 | `1` |
| `order_asc` | body | boolean | 否 | 是否创建时间升序排列 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/inboundResultNotify?app_key=your_appkey_here&method=wms.inboundResultNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 响应状态码 | `200` |
| `msg` | string | 响应信息 | `success` |
| `order_list` | array | 售后单信息列表 | `` |
| `total` | number | 当前搜索条件下，匹配到的总数量 | `200` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1020） | 参数修改 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000） | 重试 |
| `20000` | 系统错误 / 业务处理失败（sub_code: isp.service-error:1040） | 根据提示处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-1） | 业务处理失败 |

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
  "sub_code": "isv.parameter-invalid:1020",
  "sub_msg": "参数错误"
}
```

## 备注
