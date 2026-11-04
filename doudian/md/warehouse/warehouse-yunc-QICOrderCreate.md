# 云仓QIC订单创建

> yunc.QICOrderCreate — 云仓QIC订单创建接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 云仓QIC订单创建 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-QICOrderCreate` |
| 接口 ID | `doudian.warehouse.yunc.QICOrderCreate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/QICOrderCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2665 |
| 更新日期 | `2022-10-27` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 否 | 外部业务单号 仅支持纯数字字符串，长度小于20 必填 | `22334234546456` |
| `BIC_order_detail` | body | object | 否 | 必填 | `` |
| `  └ external_shop_id` | body | string | 否 | 外部店铺ID 仅支持纯数字字符串 必填 | `1422534` |
| `  └ user_id` | body | string | 否 | 外部店铺ID | `4300291` |
| `  └ warehouse_code` | body | string | 否 | 质检仓编码 必填 | `SC-BIC-SH` |
| `  └ receiver_info` | body | object | 否 | 收件人信息 必填 | `` |
| `    └ name` | body | string | 否 | 姓名 必填 | `张三` |
| `    └ phone` | body | string | 否 | 固定电话号 | `010-26321234` |
| `    └ mobile` | body | string | 否 | 手机号 必填 | `15200001234` |
| `    └ country_code` | body | string | 否 | 国家编码 必填 | `CHN` |
| `    └ province_code` | body | string | 否 | 省编码 | `01` |
| `    └ province_name` | body | string | 否 | 省名称 必填 | `北京` |
| `    └ city_code` | body | string | 否 | 城市编码 | `123` |
| `    └ city_name` | body | string | 否 | 城市名称 必填 | `北京市` |
| `    └ district_code` | body | string | 否 | 区县编码 | `345` |
| `    └ district_name` | body | string | 否 | 区县名称 必填 | `海淀区` |
| `    └ street_code` | body | string | 否 | 街道编码 | `657` |
| `    └ street_name` | body | string | 否 | 街道名称 | `中关村街道` |
| `    └ detail_address` | body | string | 否 | 详细地址 必填 | `互联网金融中心` |
| `  └ sender_info` | body | object | 否 | 寄件人信息 必填 | `` |
| `    └ name` | body | string | 否 | 姓名 必填 | `张三` |
| `    └ phone` | body | string | 否 | 固定电话号 | `010-26321234` |
| `    └ mobile` | body | string | 否 | 手机号 必填 | `15200001234` |
| `    └ country_code` | body | string | 否 | 国家编码 必填 | `CHN` |
| `    └ province_code` | body | string | 否 | 省编码 | `01` |
| `    └ province_name` | body | string | 否 | 省名称 必填 | `北京` |
| `    └ city_code` | body | string | 否 | 城市编码 | `123` |
| `    └ city_name` | body | string | 否 | 城市名称 必填 | `北京市` |
| `    └ district_code` | body | string | 否 | 区县编码 | `123` |
| `    └ district_name` | body | string | 否 | 区县名称 必填 | `海淀区` |
| `    └ street_code` | body | string | 否 | 街道编码 | `43245` |
| `    └ street_name` | body | string | 否 | 街道名称 | `中关村街道` |
| `    └ detail_address` | body | string | 否 | 详细地址 必填 | `互联网金融中心` |
| `  └ buyer_remark` | body | string | 否 | 买家备注 | `快点发货` |
| `  └ seller_remark` | body | string | 否 | 卖家备注 | `越快越好` |
| `  └ book_time` | body | number | 否 | 下单时间 秒级时间戳 | `1666868569` |
| `  └ pay_time` | body | number | 否 | 支付时间 秒级时间戳 | `1666868569` |
| `  └ promise_sign_time` | body | number | 否 | 期望收货时间 秒级时间戳 | `1666868569` |
| `  └ order_amount` | body | number | 否 | 订单费用 单位（分） | `123` |
| `  └ freight_amount` | body | number | 否 | 运费 单位（分） | `456` |
| `  └ pay_amount` | body | number | 否 | 支付费用 单位（分） | `789` |
| `  └ is_allow_merge` | body | string | 否 | 是否合单 1-合单，2-非合单 默认非合单 | `1` |
| `  └ source_platform_code` | body | string | 否 | 订单来源平台 DY-抖音 | `DY` |
| `BIC_product_infos` | body | array | 否 | 商品明细 必填 | `` |
| `  └ product_id` | body | string | 否 | 商品ID 必填 | `1234` |
| `  └ product_name` | body | string | 否 | 商品名称 必填 | `新疆玉石` |
| `  └ sku_id` | body | number | 否 | skuId 必填 | `3424` |
| `  └ spec_info` | body | string | 否 | 规格信息 | `玉` |
| `  └ count` | body | string | 否 | 数量 必填 | `2` |
| `  └ sku_price` | body | number | 否 | 价格 必填 | `2034` |
| `  └ sku_desc` | body | string | 否 | sku描述 | `玉` |
| `  └ pic_url` | body | string | 否 | 商品图片的url 必填 | `https://p3-aio.ecombdimg.com/obj/temai/Fq8p6AbLZdvWsVWRhEVBqsy6CmQB` |
| `  └ unit` | body | string | 否 | 单位 | `块` |
| `  └ cargo_code` | body | string | 否 | 平台货品id | `7004716017276518700` |
| `  └ bar_code` | body | string | 否 | 条码 | `6975482081806` |
| `  └ first_category_id` | body | string | 否 | 一级类目ID | `955400` |
| `  └ second_category_id` | body | string | 否 | 二级类目ID | `955401` |
| `  └ third_category_id` | body | string | 否 | 三级类目ID | `955402` |
| `  └ fourth_category_id` | body | string | 否 | 四级类目ID | `955403` |
| `  └ first_category_name` | body | string | 否 | 一级类目名称 | `珠宝与衍生品` |
| `  └ second_category_name` | body | string | 否 | 二级类目名称 | `天然水晶` |
| `  └ third_category_name` | body | string | 否 | 三级类目名称 | `天然水晶摆挂件` |
| `  └ fourth_category_name` | body | string | 否 | 四级类目名称 | `天然水晶摆挂件` |
| `extend` | body | string | 否 | 需要在"origin_track_no"key中填写原始运单号  必填 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
