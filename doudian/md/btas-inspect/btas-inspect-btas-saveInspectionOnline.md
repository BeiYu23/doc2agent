# 商家_商家送检图片质检（线上质检）订单

> btas.saveInspectionOnline — 商家_商家送检图片质检（线上质检）订单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家_商家送检图片质检（线上质检）订单 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-saveInspectionOnline` |
| 接口 ID | `doudian.btas-inspect.btas.saveInspectionOnline` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/saveInspectionOnline` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/572 |
| 更新日期 | `2021-06-07` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 父订单（店铺单）编号 | `4775168038676399798` |
| `product_order_id` | body | string | 是 | 商品单ID | `4775168038676399799` |
| `order_code` | body | string | 是 | 一件商品一个订单码，订单码由字节系统生成。 订单码 | `0123456787` |
| `service_status` | body | string | 是 | 枚举值 1: 新增   2: 修改 | `1` |
| `certification_code` | body | string | 是 | 质检扣 | `Q12312312312` |
| `is_original_info` | body | string | 是 | 原盒包装 枚举值 1: 是  2: 否 | `1` |
| `brand_id` | body | number | 是 | 鉴定品牌，列表参数见接口 btas/listBrand | `2` |
| `return_intercept_type` | body | string | 是 | 0：发货优先，送检前存在退款申请可通过送检自动拒绝   1：售后优先：送检前存在退款申请则不可送检 | `0` |
| `images` | body | array | 是 | 送检图片 | `` |
| `  └ image_id` | body | number | 是 | 图片ID 要求大于0 | `1` |
| `  └ image_url` | body | string | 是 | 图片链接 | `"https://xxx.xxxx.xxxx"` |
| `  └ image_comment` | body | string | 否 | 图片备注 | `"带扣"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/saveInspectionOnline?app_key=your_appkey_here&method=btas.saveInspectionOnline&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2038:鉴定扣已使用（sub_code: isv.business-failed:2038） | 更换 |
| `50002` | 业务处理失败 / 2027:线下质检订单请通过管理系统进行操作（sub_code: isv.business-failed:2027） | - |
| `50002` | 业务处理失败 / 10000:订单目前不满足送检条件，请检查取消状态或所绑定质检机构（sub_code: isv.business-failed:10000） | - |
| `50002` | 业务处理失败 / 2036:拦截发货时候请先处理退款请求（sub_code: isv.business-failed:2036） | - |

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
  "sub_code": "isv.business-failed:2038",
  "sub_msg": "2038:鉴定扣已使用"
}
```

## 备注
