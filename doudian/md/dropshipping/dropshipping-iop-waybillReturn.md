# iop.waybillReturn

> 回传物流单号，实现代发订单的发货功能（注：回传成功后，原始订单也会同步更新成已发货状态）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.waybillReturn` |
| 中文名 | 回传物流单号 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/waybillReturn` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/676 |
| 更新日期 | `2022-08-01` |

## 接口说明

- 文档书: 代发API（版本 V6.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | number | 是 | 代打店铺id | `543123423` |
| `distr_order_id` | body | string | 是 | 代打订单号 | `884334435345` |
| `company_code` | body | string | 否 | 物流公司，当包裹list为空或不合规时，该字段必填；后续即将废弃，建议传入pack_list； | `jd` |
| `track_no` | body | string | 否 | 面单号，当包裹list为空或不合规时，该字段必填；后续即将废弃，建议传入pack_list； | `12345` |
| `is_refund_reject` | body | boolean | 否 | 是否拒绝退款申请（默认不传即为false，则发货失败；true即拒绝退款，发货成功 | `false` |
| `address_id` | body | number | 否 | 1商家后台-地址库管理里获取。如果send_addr不为空，则以send_addr的为准 | `882134` |
| `send_addr` | body | object | 否 | 发货地址 | `` |
| `  └ province` | body | object | 是 | 省 | `` |
| `    └ id` | body | string | 是 | 省编码 | `43` |
| `    └ name` | body | string | 是 | 省名称 | `广东省` |
| `  └ city` | body | object | 是 | 市 | `` |
| `    └ id` | body | string | 是 | 市编码 | `31` |
| `    └ name` | body | string | 是 | 市名称 | `深圳市` |
| `  └ town` | body | object | 是 | 区 | `` |
| `    └ id` | body | string | 是 | 区编码 | `55` |
| `    └ name` | body | string | 是 | 区名称 | `南山区` |
| `  └ detail` | body | string | 是 | 详情 | `xxxx社区xxx楼xxx房` |
| `  └ landmark` | body | string | 是 | 直接传空字符串 | `直接传空字符串` |
| `  └ street` | body | object | 是 | 街道 | `` |
| `    └ id` | body | string | 是 | 街道编码 | `5551` |
| `    └ name` | body | string | 是 | 街道名称 | `xx街道` |
| `pack_list` | body | array | 否 | 当物流公司和面单号均为空时，该字段为必填；当该字段不为空时，以该字段信息为准。 | `` |
| `  └ track_no` | body | string | 是 | 运单号 | `12345` |
| `  └ ship_num` | body | number | 是 | 代发单的待发货件数 | `1` |
| `  └ company_code` | body | string | 是 | 物流公司 | `jd` |
| `serial_number_list` | body | array | 否 | 序列号 | `["546443524543534","646443524543534"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillReturn?app_key=your_appkey_here&method=iop.waybillReturn&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `return_result` | boolean | 结果 | `true` |
| `delivery_id` | string | 运单id | `982734` |
| `pack_list` | array | 包裹信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 请检查参数 |
| `50002` | 业务处理失败 / 代打订单状态不允许发货（sub_code: isv.business-failed:41001） | 请检查代发单状态 |
| `50002` | 业务处理失败 / 代打订单状态不允许发货（sub_code: isv.business-failed:41000） | 请检查代发单状态 |
| `50002` | 业务处理失败 / 代打订单状态不允许发货（sub_code: isv.business-failed:41004） | 请检查代发单状态 |
| `50002` | 业务处理失败 / 代发单不存在（sub_code: isv.business-failed:41002） | 请检查代发单是否存在 |
| `50002` | 业务处理失败 / 没有找到默认的发货地址（sub_code: isv.business-failed:41003） | 没有找到默认的发货地址，请到抖店后台配置 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:88888） | 发货失败，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10005） | 发货失败，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10006） | 发货失败，请稍后重试 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:1000） | 发货失败，请稍后重试 |
| `50002` | 业务处理失败 / 发货失败，请重新检查当前请求发货的全部件数，等于代发单的剩余待发货件数（sub_code: isv.business-failed:41007） | 发货失败，请重新检查当前请求发货的全部件数，等于代发单的剩余待发货件数 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "982734",
    "pack_list": [
      {
        "company_code": "jd",
        "deliver_id": "982734",
        "ship_num": "1",
        "track_no": "12345"
      }
    ],
    "return_result": "true"
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
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "参数错误"
}
```

## 备注
