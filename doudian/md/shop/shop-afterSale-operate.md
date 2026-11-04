# 售后审核接口聚合版

> afterSale.operate — 售后审核接口聚合版

| 元信息 | 值 |
| --- | --- |
| 中文名 | 售后审核接口聚合版 |
| 文档地址 | `/docs/doudian/shop/shop-afterSale-operate` |
| 接口 ID | `doudian.shop.afterSale.operate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/operate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2037 |
| 更新日期 | `2022-06-27` |

## 接口说明

- 文档书: 店铺API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `type` | body | string | 是 | 操作类型；请查看API描述枚举值说明 | `111` |
| `items` | body | array | 是 | 操作售后详情 | `` |
| `  └ aftersale_id` | body | string | 是 | 售后单号 | `6959800000297566494` |
| `  └ reason` | body | string | 否 | 操作原因，拒绝操作必填 | `商品有破损` |
| `  └ remark` | body | string | 否 | 操作评论，拒绝操作必填 | `商品有污渍，影响二次销售` |
| `  └ evidence` | body | array | 否 | 操作凭证编码，当【afterSale/rejectReasonCodeList】接口响应参数evidence_need=Y时，该参数必填；使用【afterSale/rejectReasonCodeList】接口获取响应参数中的reject_reason_code字段。 | `` |
| `    └ type` | body | string | 否 | 凭证类型，1:图片，2:视频，3:音频(暂不支持展示)，4:文字(暂不支持展示)。“用户可见备注”为remark字段 | `0` |
| `    └ url` | body | string | 否 | 凭证url | `http://xxxxxxxx.jpg` |
| `    └ desc` | body | string | 否 | 凭证描述 | `过敏部位图片` |
| `  └ logistics` | body | object | 否 | 同意退货/同意换货物流信息，当前type=101，301，311是该集合需要传值。 | `-` |
| `    └ company_code` | body | string | 否 | 物流公司code，使用【/order/logisticsCompanyList】接口获取；type=311仅换货时需要填入 | `yuantong` |
| `    └ logistics_code` | body | string | 否 | 物流单号（快递单号），仅type=311仅换货时需要填入 | `YT31368712931` |
| `    └ receiver_address_id` | body | number | 否 | 收件地址id（推荐使用），必须通过【/address/list】获取【address_id】填入。和after_sale_address_detail字段集合二选一； | `95251` |
| `    └ sender_address_id` | body | number | 否 | 已废弃字段，（隐藏时间20220610）发件地址id | `95252` |
| `    └ after_sale_address_detail` | body | object | 否 | 商家同意退货/同意换货收件地址详情（不推荐使用）；和receiver_address_id字段二选一（推荐使用）；商家可以自定义退货地址。 | `-` |
| `      └ province_name` | body | string | 否 | 省；使用【/address/getProvince】接口获取 | `北京` |
| `      └ city_name` | body | string | 否 | 市；需要使用【/address/getAreasByProvince】接口响应参数获取 | `北京` |
| `      └ town_name` | body | string | 否 | 区；需要使用【/address/getAreasByProvince】接口响应参数获取 | `海淀` |
| `      └ detail` | body | string | 否 | 地址详情 | `北京市海淀区丹棱街1号305` |
| `      └ user_name` | body | string | 否 | 收件人 | `张三` |
| `      └ mobile` | body | string | 否 | 联系电话，支持手机号和固定电话；固定电话需要传入区号。注意：区号和号码之间一定要传入“-”传值示例：0571-1234567；否则会报错电话号码不合法。 | `17777777777` |
| `      └ street_name` | body | string | 否 | 街道名称 | `丹棱街` |
| `      └ province_id` | body | number | 否 | 省id；使用【/address/getProvince】接口获取 | `10` |
| `      └ city_id` | body | number | 否 | 市id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `10` |
| `      └ town_id` | body | number | 否 | 区id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `01` |
| `      └ street_id` | body | number | 否 | 街道id；需要使用【/address/getAreasByProvince】接口响应参数获取 | `12` |
| `  └ reject_reason_code` | body | number | 否 | 售后拒绝原因码，拒绝时必填填。通过/afterSale/rejectReasonCodeList获取 | `1` |
| `  └ update_time` | body | number | 否 | 售后版本 | `0` |
| `store_id` | body | number | 否 | 门店ID | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/operate?app_key=your_appkey_here&method=afterSale.operate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 审核结果 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误，电话号码不合法（sub_code: isv.parameter-invalid:11000） | 检查电话号码后重试 |
| `20000` | 系统错误 / 存在无效的售后单（sub_code: isp.service-error:10000） | 检查售后单后重试 |
| `20000` | 系统错误 / 返回内容为空，重试后若错误继续存在，请联系平台（sub_code: isp.service-error:10002） | 重试 |
| `50002` | 业务处理失败 / 操作失败（sub_code: isv.business-failed:11005） | 检查后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "aftersale_id": "6959800000297566494",
        "status_code": "0",
        "status_msg": "success"
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误，电话号码不合法"
}
```

## 备注
