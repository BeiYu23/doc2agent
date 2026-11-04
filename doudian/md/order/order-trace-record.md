# 在订单链路监控场景中，回传轨迹信息

> trace.record — 在订单链路监控场景中，回传轨迹信息。 信息回传后能自动记录并统计监控状态信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 在订单链路监控场景中，回传轨迹信息 |
| 文档地址 | `/docs/doudian/order/order-trace-record` |
| 接口 ID | `doudian.order.trace.record` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trace/record` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/2796 |
| 更新日期 | `2022-12-19` |

## 接口说明

- 文档书: 订单API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单ID | `4996000714287787069` |
| `status` | body | string | 是 | 轨迹状态。ERP_TRANSFER(完成转单)，ERP_CHECK(完成审单)，CP_NOTIFY(完成通知仓储配货)，ACCEPT(仓库接单完成)，PRINT(完成打印拣货单/完成打印面单)，PICK(完成拣货)，CHECK(拣货复核完成)，PACKAGE(仓库完成打包)，CONFIRM(仓库通知ERP出货) | `ERP_CHECK` |
| `record_time` | body | string | 是 | 业务动作发生时间；格式：yyyy-MM-dd HH:mm:ss | `2022-11-01 00:00:00` |
| `ext_info` | body | object | 否 | 扩展信息 | `` |
| `  └ out_operator` | body | string | 否 | 当前操作人 | `**店:小王` |
| `  └ out_wms_app` | body | string | 否 | 关联wms的app信息 | `12497914` |
| `  └ out_customer_id` | body | string | 否 | 货主在wms的身份标识 | `BJ121` |
| `  └ remark` | body | string | 否 | 备注信息 | `自动流转` |
| `warehouse_code` | body | string | 否 | 仓编码 | `CP121212` |
| `product_list` | body | array | 否 | 仓商品信息 | `` |
| `  └ sku_order_id` | body | string | 是 | 子订单ID | `4996000714287787070` |
| `  └ count` | body | number | 是 | 商品数量 | `1` |
| `  └ sub_product_info_list` | body | array | 否 | 组套商品信息，非组套商品请勿传入 | `` |
| `    └ sku_id` | body | string | 是 | 商品SkuId | `30714287782120` |
| `    └ product_id` | body | string | 是 | 商品Id | `30714287787070` |
| `    └ count` | body | number | 是 | 商品数量 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.commengru/test/encrypt/v1?app_key=your_appkey_here&method=mengru.test.encrypt.v1&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误,订单不存在（sub_code: isv.parameter-invalid:605090050） | 填写正确的订单ID |
| `40004` | 非法的参数 / 当前用户已关闭订单轨迹服务（sub_code: isv.parameter-invalid:605090005） | 可调用/trace/addShop接口重新开通 |
| `40004` | 非法的参数 / 当前用户授权已过期，轨迹记录服务自动关闭（sub_code: isv.parameter-invalid:605090006） | 店铺对App重新授权后自动开启 |
| `40004` | 非法的参数 / 参数错误, 未定义的Status（sub_code: isv.parameter-invalid:605090013） | 请填写正确的Status |
| `40004` | 非法的参数 / 参数错误，RecordTime格式不正确（sub_code: isv.parameter-invalid:605090014） | 业务时间格式为：2022-11-30 10:52:53 |
| `40004` | 非法的参数 / 轨迹信息已回传,请不要重复处理,系统将使用第一次回传记录（sub_code: isv.parameter-invalid:605090015） | 无需处理，系统将采用第一次回传记录 |
| `40004` | 非法的参数 / 轨迹信息异常, 订单状态回传不正确,下一状态应为**（sub_code: isv.parameter-invalid:605090021） | 请填写正确的Status |
| `40004` | 非法的参数 / 轨迹信息异常, 订单缺少前置状态（sub_code: isv.parameter-invalid:605090020） | 请填写正确的Status |
| `40004` | 非法的参数 / 轨迹信息异常, 订单当前状态业务时间晚于前置状态（sub_code: isv.parameter-invalid:605090022） | 请填写正确的业务时间 |
| `20000` | 系统错误 / 内部服务异常，请稍后重试（sub_code: isp.service-error:605090001） | 内部服务异常，请稍后重试 |
| `40004` | 非法的参数 / 参数错误，RecordTime不能早于当前时间（sub_code: isv.parameter-invalid:605090023） | 请填写正确的业务时间 |
| `40004` | 非法的参数 / 当前应用与店铺间授权失效，请检查店铺授权（sub_code: isv.parameter-invalid:605010102） | 请引导店铺重新对应用授权 |

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
  "sub_code": "isv.parameter-invalid:605090050",
  "sub_msg": "参数错误,订单不存在"
}
```

## 备注
