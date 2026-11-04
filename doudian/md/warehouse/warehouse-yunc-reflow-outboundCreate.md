# yunc.reflow.outboundCreate

> 翻仓出库单创建接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.reflow.outboundCreate` |
| 中文名 | 翻仓出库单创建 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/reflow/outboundCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2276 |
| 更新日期 | `2022-11-03` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W1009` |
| `outbound_order_no` | body | string | 是 | 出库单号 | `OO123456` |
| `biz_order_no` | body | string | 是 | 上游业务单号 | `123456` |
| `owner_code` | body | string | 否 | 货主编码 | `BD10000028` |
| `owner_name` | body | string | 否 | 货主名称 | `测试货主` |
| `shopid` | body | number | 否 | 店铺ID | `1111235707` |
| `shop_name` | body | string | 否 | 店铺名称 | `测试店铺` |
| `order_type` | body | string | 是 | 单据类型（XSCK-销售出库，TCCK-退仓出库，DBCK-调拨出库，SCCK-生产出库，QTCK-其他出库） | `XSCK` |
| `status` | body | string | 是 | 单据状态（1-创单成功） | `10` |
| `express` | body | string | 否 | 快递商编码 | `zhongtong` |
| `express_name` | body | string | 否 | 快递商名称 | `中通速递` |
| `sender_info` | body | object | 否 | 发货人信息 | `` |
| `  └ province_code` | body | string | 否 | 省编号 | `44` |
| `  └ province` | body | string | 否 | 省名称 | `广东省` |
| `  └ city_code` | body | string | 否 | 市编号 | `440100` |
| `  └ city` | body | string | 否 | 市名称 | `广州市` |
| `  └ district_code` | body | string | 否 | 区编号 | `440106` |
| `  └ district` | body | string | 否 | 区名称 | `天河区` |
| `  └ street_code` | body | string | 否 | 街道编号 | `xxxx` |
| `  └ street` | body | string | 否 | 街道 | `xxxx街道` |
| `  └ name` | body | string | 否 | 姓名 | `xxxx` |
| `  └ mobile` | body | string | 否 | 手机 | `xxxxxxxxxx` |
| `  └ detail` | body | string | 否 | 详细地址 | `广东省广州市天河区xxx街道xx号xx室` |
| `  └ telephone` | body | string | 否 | 固定电话 | `xxxxxxxxxx` |
| `receiver_info` | body | object | 否 | 收货人信息 | `` |
| `  └ province_code` | body | string | 否 | 省编号 | `23` |
| `  └ province` | body | string | 否 | 省名称 | `黑龙江省` |
| `  └ city_code` | body | string | 否 | 市编号 | `232700` |
| `  └ city` | body | string | 否 | 市名称 | `大兴安岭地区` |
| `  └ district_code` | body | string | 否 | 区编号 | `232724` |
| `  └ district` | body | string | 否 | 区名称 | `大兴安岭辖区` |
| `  └ street_code` | body | string | 否 | 街道编号 | `xxxx` |
| `  └ street` | body | string | 否 | 街道 | `xxxx街道` |
| `  └ name` | body | string | 否 | 姓名 | `xxxx` |
| `  └ mobile` | body | string | 否 | 手机 | `xxxxxxxxxx` |
| `  └ detail` | body | string | 否 | 详细地址 | `黑龙江省大兴安岭地区大兴安岭辖区xxx街道xx号xx室` |
| `  └ telephone` | body | string | 否 | 固定电话 | `xxxxxxxxxx` |
| `order_time` | body | number | 否 | 下单时间 | `1658198430` |
| `source_platform_code` | body | string | 否 | 订单来源平台编码 | `DY` |
| `source_platform_name` | body | string | 否 | 订单来源平台名称 | `抖音` |
| `remark` | body | string | 否 | 备注 | `备注内容` |
| `order_details` | body | array | 是 | 入库单明细 | `` |
| `  └ line_no` | body | string | 是 | 行号（同一出库单下行号唯一，必填） | `1` |
| `  └ cargo_code` | body | string | 是 | 货品编码（必填） | `7072665065857597721` |
| `  └ cargo_name` | body | string | 是 | 货品名称（必填） | `测试货品` |
| `  └ barcode` | body | string | 否 | 货品条码 | `123456` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品ID | `E123456` |
| `  └ expect_qty` | body | number | 是 | 预计出库数量（必填） | `10` |
| `  └ actual_qty` | body | number | 否 | 实际出库数量 | `0` |
| `order_create_time` | body | number | 否 | wms系统单据创建时间 | `1665460015` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/reflow/outboundCreate?app_key=your_appkey_here&method=yunc.reflow.outboundCreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 错误码 | `0` |
| `msg` | string | 错误信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1001:单据状态应为已创建（sub_code: isv.business-failed:1001） | 联系系统负责人处理 |
| `50002` | 业务处理失败 / 1000:业务处理失败（sub_code: isv.business-failed:1000） | 联系系统负责人处理 |
| `50002` | 业务处理失败 / 12000:获取仓库信息失败，请检查编码是否有效（sub_code: isv.business-failed:12000） | 检查仓库编码有效性 |
| `50002` | 业务处理失败 / 13002:单据正在处理中（sub_code: isv.business-failed:13002） | 请稍候重试 |
| `50002` | 业务处理失败 / 13006:调用货主服务失败（sub_code: isv.business-failed:13006） | 检查货主有效性 |
| `50002` | 业务处理失败 / 13001:货主、店铺信息不合法（sub_code: isv.business-failed:13001） | 检查货主店铺对应关系 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
  "sub_code": "isv.business-failed:1001",
  "sub_msg": "1001:单据状态应为已创建"
}
```

## 备注
