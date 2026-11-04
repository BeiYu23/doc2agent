# 云仓出库接单

> yunc.cloudCreateOutboundOrder — 云仓出库接单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 云仓出库接单 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-cloudCreateOutboundOrder` |
| 接口 ID | `doudian.warehouse.yunc.cloudCreateOutboundOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/cloudCreateOutboundOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/898 |
| 更新日期 | `2026-08-26` |

## 接口说明

- 文档书: 仓库作业API（版本 V11.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `delivery_mode` | body | mixed | 是 | 交货方式 | `1` |
| `platform_order_no` | body | string | 是 | 平台交易单号 | `1234234` |
| `erp_order_no` | body | string | 是 | ERP出库单号 | `1234234` |
| `order_type` | body | mixed | 是 | 订单类型 1:销售出库 | `1` |
| `expected_qty` | body | mixed | 是 | 应发数量 | `100` |
| `source_platform_code` | body | string | 是 | 订单来源平台编码 | `2222` |
| `source_platform_name` | body | string | 是 | 订单来源平台名称 | `德化仓` |
| `order_time` | body | mixed | 是 | 前台订单下单时间 | `1612202522000` |
| `review_time` | body | mixed | 是 | 审单时间 | `1612202522000` |
| `express_code` | body | string | 是 | 快递公司编码 | `shunfeng` |
| `express_name` | body | string | 否 | 快递公司名称 | `顺丰` |
| `is_insure` | body | mixed | 是 | 是否保价 | `1` |
| `insure_amount` | body | mixed | 否 | 保价金额 | `1000` |
| `express_product_id` | body | string | 否 | 快递产品类型 | `shunfeng001` |
| `express_product_name` | body | string | 否 | 快递产品名称 | `顺丰次日达` |
| `shop_id` | body | mixed | 是 | DY传shopid，非DY传erp的店铺编码 | `2345` |
| `allow_merge` | body | mixed | 是 | 是否允许合单 | `1` |
| `sender_info` | body | object | 是 | 发件人信息 | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ city` | body | string | 是 | 城市名称（必传） | `合肥市` |
| `  └ tel_phone` | body | string | 否 | 固定电话 | `15677711111` |
| `  └ district_code` | body | string | 否 | 地区编码 | `003` |
| `  └ detail` | body | string | 是 | 详细地址（必传） | `西溪八方城` |
| `  └ street_code` | body | string | 否 | 街道编码 | `004` |
| `  └ mobile` | body | string | 否 | 联系方式 | `15677711111` |
| `  └ province` | body | string | 是 | 省份名称（必传） | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `002` |
| `  └ street` | body | string | 否 | 街道名称 | `闲林街道` |
| `  └ district` | body | string | 是 | 地区名称（必传） | `蜀山区` |
| `  └ name` | body | string | 是 | 姓名 | `张三` |
| `  └ oaids` | body | string | 否 | 地址id | `地址id` |
| `receiver_info` | body | object | 是 | 收件人信息 | `` |
| `  └ province` | body | string | 是 | 省份名称（必传） | `安徽省` |
| `  └ city` | body | string | 是 | 城市名称（必传） | `合肥市` |
| `  └ street` | body | string | 否 | 街道名称 | `闲林街道` |
| `  └ city_code` | body | string | 否 | 城市编码 | `002` |
| `  └ tel_phone` | body | string | 否 | 固定电话 | `18766611111` |
| `  └ district_code` | body | string | 否 | 地区编码 | `003` |
| `  └ oaids` | body | string | 否 | 地址id | `地址id` |
| `  └ name` | body | string | 是 | 姓名 | `李四` |
| `  └ detail` | body | string | 是 | 详细地址（必传） | `西溪八方城` |
| `  └ mobile` | body | string | 否 | 联系方式 | `18766611111` |
| `  └ district` | body | string | 是 | 地区名称（必传） | `蜀山区` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ street_code` | body | string | 否 | 街道编码 | `004` |
| `remark` | body | string | 否 | 备注 | `轻拿轻放` |
| `buyer_message` | body | string | 否 | 买家备注 | `放门口` |
| `seller_message` | body | string | 否 | 卖家备注 | `贵重物品` |
| `order_details` | body | array | 是 | 订单详情 | `` |
| `  └ order_time` | body | mixed | 否 | 下单时间 | `1649833646` |
| `  └ cargo_code` | body | string | 否 | 平台货品编码 | `23232` |
| `  └ platform_order_no` | body | string | 否 | 平台订单号 | `999891234567010821` |
| `  └ category_name` | body | string | 否 | 类目名称 | `服饰` |
| `  └ barcode` | body | string | 否 | 货品条码（barcode字段要求为4-19位） | `23423423` |
| `  └ sku_name` | body | string | 是 | 商品名称 | `鲜花` |
| `  └ erp_sku_id` | body | string | 否 | ERP商品编码 | `23234234` |
| `  └ pay_time` | body | mixed | 否 | 支付时间 | `1649833646` |
| `  └ product_date` | body | mixed | 否 | 生产日期 | `1612202522000` |
| `  └ inventory_type` | body | mixed | 是 | 库存类型 1正品 2次品 | `1` |
| `  └ expire_date` | body | mixed | 否 | 过期日期 | `1612202522000` |
| `  └ subplatform_order_no` | body | string | 否 | 平台交易子订单号 | `999891234567010821` |
| `  └ line_no` | body | string | 是 | 出库单行号 | `22323` |
| `  └ merge_shop_id` | body | mixed | 否 | 店铺ID | `1111241785` |
| `  └ expected_qty` | body | mixed | 是 | 订单数量 | `12` |
| `  └ platform_sku_id` | body | string | 否 | 平台商品编码 | `11` |
| `  └ batch_code` | body | string | 否 | 批次号 | `1` |
| `  └ inventory_status` | body | mixed | 是 | 库存状态 1正常 2质检 3冻结 | `1` |
| `warehouse_code` | body | string | 否 | 仓编码 | `1` |
| `owner_code` | body | string | 否 | 货主编码(必填！！) | `11` |
| `add_biz_type` | body | string | 否 | 附加业务类型 A100:代发 | `A100` |
| `out_batch_num` | body | mixed | 否 | 合单数量 | `2` |
| `package_type` | body | mixed | 否 | 订单类型（一单一包:1 拆单:2 合单:3） | `3` |
| `pay_time` | body | mixed | 否 | 支付时间 | `161220252` |
| `shop_name` | body | string | 否 | 店铺名称 | `测试店铺` |
| `extend` | body | string | 否 | 扩展字段 | `{key:val}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cloudCreateOutboundOrder?app_key=your_appkey_here&method=yunc.cloudCreateOutboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 货品不存在（sub_code: isv.business-failed:62302630） | 货品信息校验不通过，按提示修改 |
| `50002` | 业务处理失败 / 承运商不存在（sub_code: isv.business-failed:100100） | 根据提示修改，请检查快递编码 |
| `50002` | 业务处理失败 / 1002:Redis加锁失败（sub_code: isv.business-failed:1002） | 并发推送出库单失败，请重试 |
| `50002` | 业务处理失败 / 62302604:获取lo失败（sub_code: isv.business-failed:62302604） | 请重试 |
| `50002` | 业务处理失败 / 62302625:接收订单异常，商家未入驻（sub_code: isv.business-failed:62302625） | 商家未入驻云仓，请检查是否开通云仓服务 |
| `50002` | 业务处理失败 / 500:500（sub_code: isv.business-failed:500） | 请重试 |
| `50002` | 业务处理失败 / 1001:并发处理失败（sub_code: isv.business-failed:1001） | 并发处理失败，请重试 |
| `50002` | 业务处理失败 / 62302628:快递不可达，无推荐快递（sub_code: isv.business-failed:62302628） | 快递不可达，请联系买家 |
| `50002` | 业务处理失败 / 62302605:构建物流订单失败（sub_code: isv.business-failed:62302605） | 请稍后重试 |
| `50002` | 业务处理失败 / 62301121:重复接单（sub_code: isv.business-failed:62301121） | 请检查订单信息 |
| `50002` | 业务处理失败 / 62302635:库存不足（sub_code: isv.business-failed:62302635） | 请检查库存信息 |
| `50002` | 业务处理失败 / 62302633:并发推送erp单据失败，请重新下发（sub_code: isv.business-failed:62302633） | 请重新下发！ |
| `50002` | 业务处理失败 / 62302601:调用库存中心失败（sub_code: isv.business-failed:62302601） | 请重试！ |
| `50002` | 业务处理失败 / 1249:该订单已存在，无需重复下发（sub_code: isv.business-failed:1249） | 无需重复下发！ |
| `50002` | 业务处理失败 / 62302632:该单号已存在，请换一个手工单号重新下发（sub_code: isv.business-failed:62302632） | 该单号已存在，请换一个手工单号重新下发 |
| `50002` | 业务处理失败 / 999999:下游RPC超时（sub_code: isv.business-failed:999999） | 请重试！ |
| `20001` | 内部服务超时 / 1103:请求内部服务超时（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / -20001:没有足够的预占产能释放（sub_code: isv.business-failed:-20001） | 没有足够的预占产能释放 |
| `50002` | 业务处理失败 / 1003:请求内部服务异常,请重试（sub_code: isv.business-failed:1003） | 请重试 |
| `50002` | 业务处理失败 / 62302606:构建物流履行单失败（sub_code: isv.business-failed:62302606） | 构建物流履行单失败 |
| `50002` | 业务处理失败 / 1271:手工单号重复，请更换（sub_code: isv.business-failed:1271） | 手工单号重复，请更换 |
| `50002` | 业务处理失败 / 1200:标准化地址异常（sub_code: isv.business-failed:1200） | 标准化地址异常 |
| `50002` | 业务处理失败 / 1252:仓快递配置信息不存在（sub_code: isv.business-failed:1252） | 仓快递配置信息不存在 |
| `50002` | 业务处理失败 / 1401:规则查询缓存失败（sub_code: isv.business-failed:1401） | 规则查询缓存失败 |
| `50002` | 业务处理失败 / -1:请求详情列表（index=0）目的地-节点信息-省编码不能为空，请检查！（sub_code: isv.business-failed:-1） | 请求详情列表（index=0）目的地-节点信息-省编码不能为空，请检查！ |
| `50002` | 业务处理失败 / 1100:查询店铺与货主绑定关系失败，请重试！（sub_code: isv.business-failed:1100） | 查询店铺与货主绑定关系失败，请重试！ |
| `50002` | 业务处理失败 / 1253:货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！（sub_code: isv.business-failed:1253） | 货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！ |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_code": "isv.business-failed:62302630",
  "sub_msg": "货品不存在"
}
```

## 备注
