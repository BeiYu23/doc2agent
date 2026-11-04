# 在订单链路监控场景中

> trace.batchRecord — 在订单链路监控场景中，批量(最大20条)回传轨迹信息。 信息回传后能自动记录并统计监控状态信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 在订单链路监控场景中 |
| 文档地址 | `/docs/doudian/order/order-trace-batchRecord` |
| 接口 ID | `doudian.order.trace.batchRecord` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trace/batchRecord` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/2797 |
| 更新日期 | `2022-12-19` |

## 接口说明

- 文档书: 订单API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `trace_list` | body | array | 是 | 轨迹信息列表 | `` |
| `  └ order_id` | body | string | 是 | 订单ID | `121212` |
| `  └ status` | body | string | 是 | 轨迹状态。ERP_TRANSFER(完成转单)，ERP_CHECK(完成审单)，CP_NOTIFY(完成通知仓储配货)，ACCEPT(仓库接单完成)，PRINT(完成打印拣货单/完成打印面单)，PICK(完成拣货)，CHECK(拣货复核完成)，PACKAGE(仓库完成打包)，CONFIRM(仓库通知ERP出货) | `ERP_CHECK` |
| `  └ record_time` | body | string | 是 | 业务动作发生时间；格式：yyyy-MM-dd HH:mm:ss | `2022-11-01 00:00:00` |
| `  └ ext_info` | body | object | 否 | 扩展信息 | `` |
| `    └ out_operator` | body | string | 否 | 当前操作人 | `**店:小王` |
| `    └ out_wms_app` | body | string | 否 | 关联wms的app信息 | `12497914` |
| `    └ out_customer_id` | body | string | 否 | 货主在wms的身份标识 | `BJ121` |
| `    └ remark` | body | string | 否 | 备注信息 | `自动流转` |
| `  └ warehouse_code` | body | string | 否 | 仓编码 | `CP12` |
| `  └ product_list` | body | array | 否 | 仓商品信息 | `` |
| `    └ sku_order_id` | body | string | 是 | 子订单ID | `4996000714287787070` |
| `    └ count` | body | number | 是 | 商品数量 | `1` |
| `    └ sub_product_info_list` | body | array | 否 | 子商品信息 | `` |
| `      └ sku_id` | body | string | 是 | 商品SkuId | `30714287782120` |
| `      └ product_id` | body | string | 是 | 商品Id | `30714287787070` |
| `      └ count` | body | number | 是 | 商品数量 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt/2?app_key=your_appkey_here&method=test.encrypt.2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `error_traces` | array | 有错误的轨迹信息。如无错误，则不返回 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数缺失，OrderId格式不正确（sub_code: isv.parameter-invalid:605090016） | 请填写正确的OrderId |
| `40004` | 非法的参数 / 参数缺失，Status格式不正确（sub_code: isv.parameter-invalid:605090017） | 请填写正确的Status |
| `40004` | 非法的参数 / 参数错误，RecordTime格式不正确[orderId=%s]（sub_code: isv.parameter-invalid:605090018） | 请填写正确的RecordTime |
| `40004` | 非法的参数 / 参数错误，RecordTime不能早于当前时间（sub_code: isv.parameter-invalid:605090023） | 请填写正确的RecordTime |
| `20000` | 系统错误 / 内部服务异常，请稍后重试（sub_code: isp.service-error:605090001） | 内部服务异常，请稍后重试 |
| `40004` | 非法的参数 / 参数错误,订单不存在（sub_code: isv.parameter-invalid:605090050） | 请填写正确的OrderId |
| `40004` | 非法的参数 / 当前用户已关闭订单轨迹服务（sub_code: isv.parameter-invalid:605090005） | 可调用/trace/addShop接口重新开通 |
| `40004` | 非法的参数 / 当前用户授权已过期，轨迹记录服务自动关闭（sub_code: isv.parameter-invalid:605090006） | 店铺对App重新授权后自动开启 |
| `50002` | 业务处理失败 / 605090025:参数错误，批量回传每次最多支持50条记录（sub_code: isv.business-failed:605090025） | 605090025:参数错误，批量回传每次最多支持50条记录 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "2"
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
  "sub_code": "isv.parameter-invalid:605090016",
  "sub_msg": "参数缺失，OrderId格式不正确"
}
```

## 备注
